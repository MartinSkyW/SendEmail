# SendEmail
Shell script tool to send email notifications

## v1.0.0
### Updated on 2026-Sep-27


## About

The **SendEmail** script is a tool that makes it simple and easy to send email notifications from the CLI or from within any other script. It leverages the shared Custom Email Library script (**/jffs/addons/shared-libs/CustomEMailFunctions.lib.sh**) to send the emails, and the AMTM email configuration file which provides the user-defined email settings.


## License

**SendEmail** is free and open-source software licensed under the
[GNU General Public License version 3.0](LICENSE).

Official SendEmail releases are maintained through this repository:

**https://github.com/Martinski4GitHub/SendEmail**


### Project Author

- **Original Author & Creator:**  @Martinski W.


## Prerequisites

- An ASUS router running **Asuswrt-Merlin** firmware.
- The JFFS scripts feature must be enabled in the firmware.
- Access to the router's command line interface via the SSH server (i.e. Dropbear)
- The user-defined email settings must be configured via AMTM (see '**em.  Email settings**' option).


## Installation

**Manual Installation**

1. To download the script to your router, use the following commands:

```bash
curl  -LSs --retry 3 --retry-delay 5 --retry-connrefused \
https://raw.githubusercontent.com/Martinski4GitHub/SendEmail/master/SendEmail.sh \
-o /jffs/scripts/SendEmail.sh && chmod a+x /jffs/scripts/SendEmail.sh
```

2. To install the script, use the following command:

```bash
 /jffs/scripts/SendEmail.sh -install
```

The script file is installed in the '**/jffs/addons/SendEmail.d/**' directory with a symbolic link in the '**/jffs/scripts/**' directory.

To get see the full list of command line arguments and switches, use the following command:

```bash
 /jffs/scripts/SendEmail -help
```


## Features:

To send emails, there are 3 basic calls:

1. To test and verify your current email settings from the AMTM email configuration file:

```bash
 /jffs/scripts/SendEmail -test
```


2. To send a simple one-line email where the email message string is provided in the command line:

```bash
 /jffs/script/SendEmail "Subject Line" "The Email Message Body String"
```


3. To send a multi-line/multi-paragraph email where the contents of the email message body is provided via a local text file:

```bash
 /jffs/scripts/SendEmail "Subject Line" -Body="/full/path/to/the/EmailBody.txt"
```

Other optional arguments are available if you want to add/change the "**From:**" sender ID, include an email title line, change the default format from **HTML** to **Plain Text**, or add a secondary email address that will receive emails along with the primary recipient.

To see the full description of the available arguments, run the following command:

```bash
 /jffs/scripts/SendEmail -help
```

To use the CLI menu for some available operations, simply type:

```bash
 /jffs/scripts/SendEmail
```


