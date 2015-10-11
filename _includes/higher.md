# Higher Admin User Guide

## Setup of roles for new users

Higher administrators can change the role for individual users by using the **manage roles** menu under the **Admin** menu.

## Annual permits setting

Lists of all current annual permits are availabla under **Admin0>Annual Permits** menu. Here higher administrators can download all permit details in spreadsheet format to facilate company wide parking allocations. These can then be uploaded on mass to Click2park by emailing the spreadsheet to support@netfm.org.

## Forgotten password requests.

Click2park allows higher admins to assume the role of a user within the system by first looking up a user using the Admin->Lookup menu. Then clicking on that user allows the admin to edit the users details without the need to see or know the current users password (which remains encryted even to higher admins). Here a higher admin can change a user passwword to resolve forgotten password issues. Note users can also resolve password issues directly from the desktop interface by clicking on the forgotten password link.

## Security Concerns for higher admins

Higher admins can see how is currently using the system using the Live logins menu. This lists all users who have accessed the system within the last 60 minutes. 

## Reporting

Higher administrators have full reporting rights, so can view occpancy reports for each car park, and can drill down to individual booking data for each user. All data is available in spreadsheet format, so can be downloaded for further analysis.

## Advanced system settings

### Annuala permit mode Release or Claim space

#### Release mode - default

Annual permits within Click2Park default to always being a space which is pre booked for the permit owner. When the user does not need to use the space they **Release** their annual permit space by using the **Offer my space** menu option. This then allows other users to make hotspace bookings on their space for the speficied time period that the space is not being used by the permit holder. This is 

#### Claim mode

Annual permitrs can be set to work in claim mode. IKt this setup annual permit holders have until 4pm on Thursday to claim their annual permit space for the following week. If they do not claim the space for one of mopre of the days in the following week, then the space automatically becomes available to other users after 4pm on Thursday. Click2Park is running in Claim mode.

To change click2park from the default release mode to claim mode requires a server side setting in the constants file, which can be requested by higher administrators by emailing support@netfm.org.

### Security questions

By default additional security questions, such as 'Topwn you were born in?' are not enabled on the system. These can be requested by emailing support@netfm.org. These security questions are used everytime a user changes their password, or forgets their password.

## Full list of addition settings available in constants file:-



````php

/** Special case since PR does not need v7 as part of the url. */
if(strpos($C2P_HOME, "c2pv7") > 0)
{
    $DEBUG_FLAG = false;
    $DB_NAME_PREFIX = 'c2pv7';
    $LIVE_SERVER = true;
    $APP_URL = "https://www.click2park.co.uk/$COMPANY/c2p.php";
}

$APP_URL = str_replace("Your-Company", "Your-Company", $APP_URL);

/** Used when selected site is inactive. */
$DEFAULT_SITE_NAME = "Main Site";

/** Email address feedback is sent to. */
$FEEDBACK_EMAIL = "feedback@netfm.org";

$ADMIN_FROM_EMAIL = "facilities@Your-Company.com";
$ADMIN_FROM_EMAIL_NAME = "Your-Compan Click2Park";

/** Default value for days in advance a reservation can be made. */
$DEFAULT_DAYS_IN_ADVANCE = 8;
$DEFAULT_DAYS_IN_ADVANCE_PREMIUM_USER = 22;

/** Password change period (number of days) **/
$PASSWORD_CHANGE_DAYS = 45;

/** Session timeout value in seconds. */
$SESSION_TIMEOUT = 300;
$SESSION_LIFETIME = 900;

/** Session timeouts for admin and agents. */
$ADMIN_SESSION_TIMEOUT = 3600;
$ADMIN_SESSION_LIFETIME = 21600;

/** Billing constants */
/* All Billing constants in minutes and pence */
$BILL_FREE_PERIOD = 60;
$BILL_CHARGE_PER_HOUR = .50;
$BILL_GREEN_PER_WEEK_DAY = .50;

$C2P_CONSTANT_HOTSPACE_PERMIT_LOGO_OFFSET_Y = 175;
$C2P_CONSTANT_APPLICATION_NAME = "Click2Park";
$C2P_CONSTANT_APPLICATION_NAME_LONG = "Click2Park";
$C2P_CONSTANT_EMAIL_ADDRESS_DOMAIN_LIST = array("netfm.org", "your-company.com");
$C2P_CONSTANT_RESTRICT_REGISTRATION_EMAIL = true;
$C2P_CONSTANT_COMPANY_NAME = "Your-Company";
$C2P_CONSTANT_LOOKUP_PAGE_SIZE = 500;
$C2P_CONSTANT_ACTIVE_ROLES_LIST = array(EnumType::$USER_ROLE->getName(), 
                                        EnumType::$HIGHER_ADMIN_ROLE->getName());
$C2P_FEATURE_CLAIM_PERMIT = true;
$C2P_FEATURE_RELEASE_FREE_SPACES = true;
$C2P_FEATURE_USE_SUB_DIVISION2 = false;
$C2P_FEATURE_USE_SUB_DIVISION3 = false;
$C2P_FEATURE_SHOW_PUBLIC_TRANSPORT_LINKS = false;
$C2P_FEATURE_RESERVATION_HOTSPACE_ENFORCE_REG = true;
$C2P_FEATURE_OFFER_SPACE = false;
$C2P_FEATURE_ENFORCE_PERMIT_LETTER_CC = false;
$C2P_FEATURE_RESERVATION_ALERT_PERMIT_HOLDERS = false;
````
