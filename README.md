# XDR Workaround

A script to retrieve incidents from XDR and send them via e-mail to the ticket list.

1.  The script needs an open reference ticket in order for ticket system to be able to merge the new events into it.

2.  Environment variables have to be created for each client.

| Variable | Description |
| ------ | ------ |
| API_KEY | API_KEY |
| API_KEY_ID | Key number, one customer can have several keys |
| API_URL | API_URL |
| CUSTOMER_NAME | Will appear in the email subjet |
| CUSTOMER_ID | Not used yet |
| REFERENCE_TICKET | Required by ticket system to merge tickets |
| LOG_FILE | File to keep a record of the last incident |
| LAST_INCIDENT | Previous incidents will not be reported. |



The script requires one argument, which is a json file with the customer information. An example can be seen in config/customer.json
This can be run for all customers via cronjob by sourcing the execution wrapper script execute.sh

Running in a virtualenv to ensure appropriate versions across runs

virtualenv -p "$(which python3)"

source /bin/activate

pip install --upgrade pip

pip install -r requirements.txt
