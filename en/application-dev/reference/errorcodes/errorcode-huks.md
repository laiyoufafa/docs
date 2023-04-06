# HUKS Error Codes

> **NOTE**
>
> This topic describes only module-specific error codes. For details about universal error codes, see [Universal Error Codes](errorcode-universal.md).

## 12000001 Feature Not Supported

**Error Message**

The `${messageInfo}` is not supported.

**Possible Causes**
The API is supported, but certain features in the API, such as the algorithm, are not supported.

**Solution**

Use the supported features as parameters.

## 12000002 Missing Key Algorithm Parameter
**Error Message**

Failed to obtain the `${messageInfo}`. It is not set in ParamSet.

**Possible Causes**

The key parameter is not set.

**Solution**

1. Determine the missing parameter from the error message.
2. Set the parameter.

## 12000003 Invalid Key Algorithm Parameter

**Error Message**

Invalid `${messageInfo}`.

**Possible Causes**

An invalid parameter is found.

**Solution**

1. Determine the invalid parameter from the error message.
2. Correct the invalid parameter.

## 12000004 File Error

**Error Message**

A file error can be any of the following: 

- Insufficient storage space.
- Invalid file size.
- Failed to `${messageInfo}`.


**Possible Causes**

The file operation failed.

**Solution**

1. Check whether sufficient disk space is available and whether the file system is normal.
2. Clear the disk space.

## 12000005 IPC Error

**Error Message**

An IPC error can be any of the following: 

- Failed to get messages from IPC.
- IPC `${messageInfo}`.

**Possible Causes**

The Inter-Process Communication (IPC) failed.

**Solution**

Locate and rectify the IPC failure.

## 12000006 Algorithm Library Operation Failed

**Error Message**

Crypto engine error.

**Possible Causes**

The algorithm library operation fails. The possible causes include the following:

1. The encryption and decryption on the algorithm library failed due to incorrect ciphertext data.
2. Incorrect key parameters exist.

**Solution**

1. Check and correct the ciphertext data.
2. Check and correct the key parameters.

## 12000007 Failed to Access the Key Due to Invalidated Credential

**Error Message**

This credential is invalidated permanently.

**Possible Causes**

The possible causes include the following:

1. The key is configured with the user access control attribute and becomes invalid after the password is cleared.
2. The key is configured with the user access control attribute and becomes invalid after a new biometric feature is enrolled.

**Solution**

1. Locate the cause of the authentication failure based on the log.
2. If the authentication fails due to the configuration of the access control attribute, the key cannot be used any more.

## 12000008 Failed to Access the Key Due to a Failure in Authentication Token Verification

**Error Message**

The authentication token verification failed.

**Possible Causes**

The challenge value is incorrect.

**Solution**

1. Check whether the challenge for user IAM authentication is correctly assembled.
2. If the challenge value is incorrect, modify the assembly mode, use the bytes generated by HUKS to assembly the challenge value, and pass it to user IAM for authentication.

## 12000009 Key Access Timed Out

**Error Message**

This authentication token timed out.

**Possible Causes**

The authentication failed because the authentication token timed out.

**Solution**

Initialize the key and perform the authentication again. Ensure that the difference between the current time and the authentication token generation time is less than the timeout interval.

## 12000010 Key Operation Sessions Reaches the Limit

**Error Message**

The number of key operation sessions has reached the limit.

**Possible Causes**

The number of concurrent key operation sessions has reached the maximum (15).

**Solution**

1. Check whether there are multiple key session operations (**init** operations) for the same application. If yes, modify the code to avoid concurrent invoking.
2. If the key operation sessions are set up for different applications, wait until the sessions are released.

## 12000011 The Entity Does Not Exist

**Error Message**

The entity does not exist.

**Possible Causes**

The key corresponding to the key alias does not exist.

**Solution**

1. Check whether the key alias is correctly spelled.
2. Check whether the key corresponding to the key alias is successfully generated.

## 12000012 External Error

**Error Message**

System external error.

**Possible Causes**

An external error, such as a hardware fault or file error, occurs.

**Solution**

Provide the error code and log information to the related party.

## 12000013 The Credential Does Not Exist

**Error Message**

The credential does not exist.

**Possible Causes**

The credential, such as the PIN, fingerprint, or face image, is not enrolled.

**Solution**

Enroll the credential or change the authentication type bound to the key.

## 12000014 Insufficient Memory

**Error Message**

- Insufficient memory.
- Malloc failed.


**Possible Causes**

The system memory is insufficient.

**Solution**

Release memory or restart the device.

## 12000015 Failed to Invoke Other System Services

**Error Message**

Failed to obtain the `${messageInfo}` information via UserIAM.

**Possible Causes**

The called system service has not started.

**Solution**

Wait for the system service to start and call the API again.