# HUKS

> ![icon-note.gif](public_sys-resources/icon-note.gif) **NOTE**<br/>
>
> The initial APIs of this module are supported since API version 8. Newly added APIs will be marked with a superscript to indicate their earliest API version.

Openharmony Universal KeyStore (HUKS) provides KeyStore (KS) capabilities for applications, including key management and key cryptography operations.
HUKS also provides APIs for applications to import or generate keys.

## Modules to Import

```js
import huks from '@ohos.security.huks'
```
## HuksErrorCode

Enumerates the error codes.

**System capability**: SystemCapability.Security.Huks

| Name                      | Value   | Description|
| -------------------------- | ----- | ---- |
| HUKS_SUCCESS | 0     |Success. |
| HUKS_FAILURE | -1    |Failure. |
| HUKS_ERROR_BAD_STATE | -2    |Incorrect state. |
| HUKS_ERROR_INVALID_ARGUMENT | -3    |Invalid argument. |
| HUKS_ERROR_NOT_SUPPORTED | -4    |Not supported. |
| HUKS_ERROR_NO_PERMISSION | -5    |No permission. |
| HUKS_ERROR_INSUFFICIENT_DATA | -6    |Insufficient data. |
| HUKS_ERROR_BUFFER_TOO_SMALL | -7    |Insufficient buffer. |
| HUKS_ERROR_INSUFFICIENT_MEMORY | -8    |Insufficient memory. |
| HUKS_ERROR_COMMUNICATION_FAILURE | -9    |Communication failure. |
| HUKS_ERROR_STORAGE_FAILURE | -10   |Storage failure. |
| HUKS_ERROR_HARDWARE_FAILURE | -11   |Hardware fault. |
| HUKS_ERROR_ALREADY_EXISTS | -12   |The object already exists. |
| HUKS_ERROR_NOT_EXIST | -13   |The object does not exist. |
| HUKS_ERROR_NULL_POINTER | -14   |Null pointer. |
| HUKS_ERROR_FILE_SIZE_FAIL | -15   |Incorrect file size. |
| HUKS_ERROR_READ_FILE_FAIL | -16   |Failed to read the file. |
| HUKS_ERROR_INVALID_PUBLIC_KEY | -17   |Invalid public key. |
| HUKS_ERROR_INVALID_PRIVATE_KEY | -18   |Invalid private key. |
| HUKS_ERROR_INVALID_KEY_INFO | -19   |Invalid key information. |
| HUKS_ERROR_HASH_NOT_EQUAL | -20   |The hash values are not equal. |
| HUKS_ERROR_MALLOC_FAIL | -21   |MALLOC failed. |
| HUKS_ERROR_WRITE_FILE_FAIL | -22   |Failed to write the file. |
| HUKS_ERROR_REMOVE_FILE_FAIL | -23   |Failed to delete the file. |
| HUKS_ERROR_OPEN_FILE_FAIL | -24   |Failed to open the file. |
| HUKS_ERROR_CLOSE_FILE_FAIL | -25   |Failed to close the file. |
| HUKS_ERROR_MAKE_DIR_FAIL | -26   |Failed to create the directory. |
| HUKS_ERROR_INVALID_KEY_FILE | -27   |Invalid key file. |
| HUKS_ERROR_IPC_MSG_FAIL | -28   |Incorrect IPC information. |
| HUKS_ERROR_REQUEST_OVERFLOWS | -29   |Request overflows. |
| HUKS_ERROR_PARAM_NOT_EXIST | -30   |The parameter does not exist. |
| HUKS_ERROR_CRYPTO_ENGINE_ERROR | -31   |CRYPTO ENGINE error. |
| HUKS_ERROR_COMMUNICATION_TIMEOUT | -32   |Communication timed out. |
| HUKS_ERROR_IPC_INIT_FAIL | -33   |IPC initialization failed. |
| HUKS_ERROR_IPC_DLOPEN_FAIL | -34   |IPC DLOPEN failed. |
| HUKS_ERROR_EFUSE_READ_FAIL | -35   |Failed to read eFUSE. |
| HUKS_ERROR_NEW_ROOT_KEY_MATERIAL_EXIST | -36   |New root key material exists. |
| HUKS_ERROR_UPDATE_ROOT_KEY_MATERIAL_FAIL | -37   |Failed to update the root key material. |
| HUKS_ERROR_VERIFICATION_FAILED | -38   |Failed to verify the certificate chain. |
| HUKS_ERROR_CHECK_GET_ALG_FAIL | -100  |Failed to check whether the ALG is obtained. |
| HUKS_ERROR_CHECK_GET_KEY_SIZE_FAIL | -101  |Failed to check whether the key size is obtained. |
| HUKS_ERROR_CHECK_GET_PADDING_FAIL | -102  |Failed to check whether padding is obtained. |
| HUKS_ERROR_CHECK_GET_PURPOSE_FAIL | -103  |Failed to check whether the purpose is obtained. |
| HUKS_ERROR_CHECK_GET_DIGEST_FAIL | -104  |Failed to check whether digest is obtained. |
| HUKS_ERROR_CHECK_GET_MODE_FAIL | -105  |Failed to check whether the mode is obtained. |
| HUKS_ERROR_CHECK_GET_NONCE_FAIL | -106  |Failed to check whether the nonce is obtained. |
| HUKS_ERROR_CHECK_GET_AAD_FAIL | -107  |Failed to check whether the AAD is obtained. |
| HUKS_ERROR_CHECK_GET_IV_FAIL | -108  |Failed to check whether the initialization vector (IV) is obtained. |
| HUKS_ERROR_CHECK_GET_AE_TAG_FAIL | -109  |Failed to check whether the AE flag is obtained. |
| HUKS_ERROR_CHECK_GET_SALT_FAIL | -110  |Failed to check whether the SALT is obtained. |
| HUKS_ERROR_CHECK_GET_ITERATION_FAIL | -111  |Failed to check whether the iteration is obtained. |
| HUKS_ERROR_INVALID_ALGORITHM | -112  |Invalid algorithm. |
| HUKS_ERROR_INVALID_KEY_SIZE | -113  |Invalid key size. |
| HUKS_ERROR_INVALID_PADDING | -114  |Invalid padding. |
| HUKS_ERROR_INVALID_PURPOSE | -115  |Invalid purpose. |
| HUKS_ERROR_INVALID_MODE | -116  |Invalid mode. |
| HUKS_ERROR_INVALID_DIGEST | -117  |Invalid digest. |
| HUKS_ERROR_INVALID_SIGNATURE_SIZE | -118  |Invalid signature size. |
| HUKS_ERROR_INVALID_IV | -119  |Invalid IV. |
| HUKS_ERROR_INVALID_AAD | -120  |Invalid AAD. |
| HUKS_ERROR_INVALID_NONCE | -121  |Invalid nonce. |
| HUKS_ERROR_INVALID_AE_TAG | -122  |Invalid AE tag. |
| HUKS_ERROR_INVALID_SALT | -123  |Invalid SALT. |
| HUKS_ERROR_INVALID_ITERATION | -124  |Invalid iteration. |
| HUKS_ERROR_INVALID_OPERATION | -125  |Invalid operation. |
| HUKS_ERROR_INTERNAL_ERROR | -999  |Internal error. |
| HUKS_ERROR_UNKNOWN_ERROR | -1000 |Unknown error. |


## HuksKeyPurpose

Enumerates the key purposes.

**System capability**: SystemCapability.Security.Huks

| Name                    | Value  | Description                            |
| ------------------------ | ---- | -------------------------------- |
| HUKS_KEY_PURPOSE_ENCRYPT | 1    | Used to encrypt plain text. |
| HUKS_KEY_PURPOSE_DECRYPT | 2    | Used to decrypt cipher text. |
| HUKS_KEY_PURPOSE_SIGN    | 4    | Usedd to sign data.    |
| HUKS_KEY_PURPOSE_VERIFY  | 8    | Used to verify the signed data.  |
| HUKS_KEY_PURPOSE_DERIVE  | 16   | Used to derive a key.          |
| HUKS_KEY_PURPOSE_WRAP    | 32   | Used for encrypted import.          |
| HUKS_KEY_PURPOSE_UNWRAP  | 64   | Used for encrypted export.              |
| HUKS_KEY_PURPOSE_MAC     | 128  | Used to generate a message authentication code (MAC). |
| HUKS_KEY_PURPOSE_AGREE   | 256  | Used for key agreement.      |

## HuksKeyDigest

Enumerates the digest algorithms.

**System capability**: SystemCapability.Security.Huks

| Name                  | Value  | Description                                    |
| ---------------------- | ---- | ---------------------------------------- |
| HUKS_DIGEST_NONE       | 0   | No digest algorithm. |
| HUKS_DIGEST_MD5        | 1    | MD5. |
| HUKS_DIGEST_SHA1       | 10   | SHA1. |
| HUKS_DIGEST_SHA224 | 11   | SHA-224. |
| HUKS_DIGEST_SHA256 | 12  | SHA-256. |
| HUKS_DIGEST_SHA384  | 13  | SHA-384. |
| HUKS_DIGEST_SHA512 | 14  | SHA-512. |

## HuksKeyPadding

Enumerates the padding algorithms.

**System capability**: SystemCapability.Security.Huks

| Name                  | Value  | Description                                    |
| ---------------------- | ---- | ---------------------------------------- |
| HUKS_PADDING_NONE | 0    | No padding algorithm. |
| HUKS_PADDING_OAEP | 1    | Optimal Asymmetric Encryption Padding (OAEP). |
| HUKS_PADDING_PSS | 2    | Probabilistic Signature Scheme (PSS). |
| HUKS_PADDING_PKCS1_V1_5 | 3    | PKCS1_V1_5. |
| HUKS_PADDING_PKCS5 | 4   | Public Key Cryptography Standards (PKCS) #5. |
| HUKS_PADDING_PKCS7 | 5   | PKCS #7|

## HuksCipherMode

Enumerates the cipher modes.

**System capability**: SystemCapability.Security.Huks

| Name         | Value  | Description                 |
| ------------- | ---- | --------------------- |
| HUKS_MODE_ECB | 1    | Electronic Code BLock (ECB) mode. |
| HUKS_MODE_CBC | 2    | Cipher Block Chaining (CBC) mode. |
| HUKS_MODE_CTR | 3    | Counter (CTR) mode. |
| HUKS_MODE_OFB | 4    | Output Feedback (OFB) mode. |
| HUKS_MODE_CCM | 31   | Counter with CBC-MAC (CCM) mode. |
| HUKS_MODE_GCM | 32   | Galois/Counter (GCM) mode. |

## HuksKeySize

Enumerates the key sizes.

**System capability**: SystemCapability.Security.Huks

| Name                        | Value  | Description                                      |
| ---------------------------- | ---- | ------------------------------------------ |
| HUKS_RSA_KEY_SIZE_512        | 512  | Rivest-Shamir-Adleman (RSA) key of 512 bits.       |
| HUKS_RSA_KEY_SIZE_768        | 768  | RSA key of 768 bits.       |
| HUKS_RSA_KEY_SIZE_1024       | 1024 | RSA key of 1024 bits.      |
| HUKS_RSA_KEY_SIZE_2048       | 2048 | RSA key of 2048 bits.      |
| HUKS_RSA_KEY_SIZE_3072       | 3072 | RSA key of 3072 bits.      |
| HUKS_RSA_KEY_SIZE_4096       | 4096 | RSA key of 4096 bits.      |
| HUKS_ECC_KEY_SIZE_224        | 224  | ECC key of 224 bits.       |
| HUKS_ECC_KEY_SIZE_256        | 256  | ECC key of 256 bits.       |
| HUKS_ECC_KEY_SIZE_384        | 384  | ECC key of 384 bits.       |
| HUKS_ECC_KEY_SIZE_521        | 521  | ECC key of 521 bits.       |
| HUKS_AES_KEY_SIZE_128        | 128  | AES key of 128 bits.       |
| HUKS_AES_KEY_SIZE_192        | 196  | AES key of 196 bits.       |
| HUKS_AES_KEY_SIZE_256        | 256  | AES key of 256 bits.       |
| HUKS_AES_KEY_SIZE_512        | 512  | AES key of 512 bits.       |
| HUKS_CURVE25519_KEY_SIZE_256 | 256  | Curve25519 key of 256 bits. |
| HUKS_DH_KEY_SIZE_2048        | 2048 | DH key of 2048 bits.       |
| HUKS_DH_KEY_SIZE_3072        | 3072 | DH key of 3072 bits.       |
| HUKS_DH_KEY_SIZE_4096        | 4096 | DH key of 4096 bits.       |

## HuksKeyAlg

Enumerates the key algorithms.

**System capability**: SystemCapability.Security.Huks

| Name            | Value  | Description                 |
| ---------------- | ---- | --------------------- |
| HUKS_ALG_RSA     | 1    | RSA.    |
| HUKS_ALG_ECC     | 2    | ECC.    |
| HUKS_ALG_DSA     | 3    | DSA.    |
| HUKS_ALG_AES     | 20   | AES.    |
| HUKS_ALG_HMAC    | 50   | HMAC.   |
| HUKS_ALG_HKDF    | 51   | HKDF.   |
| HUKS_ALG_PBKDF2  | 52   | PBKDF2. |
| HUKS_ALG_ECDH    | 100  | ECDH.   |
| HUKS_ALG_X25519  | 101  | X25519 algorithm. |
| HUKS_ALG_ED25519 | 102  | ED25519 algorithm. |
| HUKS_ALG_DH      | 103  | DH.     |

## HuksKeyGenerateType

Enumerates the key generation types.

**System capability**: SystemCapability.Security.Huks

| Name                          | Value  | Description            |
| ------------------------------ | ---- | ---------------- |
| HUKS_KEY_GENERATE_TYPE_DEFAULT | 0    | Key generated by default. |
| HUKS_KEY_GENERATE_TYPE_DERIVE  | 1    | Derived key. |
| HUKS_KEY_GENERATE_TYPE_AGREE   | 2    | Key generated by agreement. |

## HuksKeyFlag

Enumerates the key generation modes.

**System capability**: SystemCapability.Security.Huks

| Name                      | Value  | Description                                |
| -------------------------- | ---- | ------------------------------------ |
| HUKS_KEY_FLAG_IMPORT_KEY   | 1    | The key is imported by using the public key import API.    |
| HUKS_KEY_FLAG_GENERATE_KEY | 2    | The key is generated by using the private key generation API.    |
| HUKS_KEY_FLAG_AGREE_KEY    | 3    | The key is generated by using the key agreement API. |
| HUKS_KEY_FLAG_DERIVE_KEY   | 4    | The key is generated by using the key derivation API. |

## HuksKeyStorageType

Enumerates the key storage modes.

**System capability**: SystemCapability.Security.Huks

| Name                   | Value  | Description                          |
| ----------------------- | ---- | ------------------------------ |
| HUKS_STORAGE_TEMP       | 0    | The key is managed locally.    |
| HUKS_STORAGE_PERSISTENT | 1    | The key is managed by the HUKS service. |

## HuksSendType

Enumerates the tag transfer modes.

**System capability**: SystemCapability.Security.Huks

| Name                | Value  | Description             |
| -------------------- | ---- | ----------------- |
| HUKS_SEND_TYPE_ASYNC | 0    | The tag is sent asynchronously. |
| HUKS_SEND_TYPE_SYNC  | 1    | The tag is sent synchronously. |

## HuksTagType

Enumerates the tag data types.

**System capability**: SystemCapability.Security.Huks


| Name                 | Value     | Description                                   |
| --------------------- | ------- | --------------------------------------- |
| HUKS_TAG_TYPE_INVALID | 0 << 28 | Invalid tag type.                    |
| HUKS_TAG_TYPE_INT     | 1 << 28 | Number of the int type. |
| HUKS_TAG_TYPE_UINT    | 2 << 28 | Number of the uint type. |
| HUKS_TAG_TYPE_ULONG   | 3 << 28 | bigint.          |
| HUKS_TAG_TYPE_BOOL    | 4 << 28 | Boolean.         |
| HUKS_TAG_TYPE_BYTES   | 5 << 28 | Uint8Array.      |

## HuksTag

Enumerates the tags used to invoke parameters.

**System capability**: SystemCapability.Security.Huks

| Name                                  | Value                                      | Description                                  |
| -------------------------------------- | ---------------------------------------- | -------------------------------------- |
| HUKS_TAG_INVALID                       | HuksTagType.HUKS_TAG_TYPE_INVALID \| 0   | Invalid tag.                       |
| HUKS_TAG_ALGORITHM                     | HUKS_TAG_TYPE_UINT \| 1                  | Algorithm.                       |
| HUKS_TAG_PURPOSE                       | HuksTagType.HUKS_TAG_TYPE_UINT \| 2      | Purpose of a key.                   |
| HUKS_TAG_KEY_SIZE                      | HuksTagType.HUKS_TAG_TYPE_UINT \| 3      | Key size.                   |
| HUKS_TAG_DIGEST                        | HuksTagType.HUKS_TAG_TYPE_UINT \| 4      | Digest algorithm.                   |
| HUKS_TAG_PADDING                       | HuksTagType.HUKS_TAG_TYPE_UINT \| 5      | Padding algorithm.                   |
| HUKS_TAG_BLOCK_MODE                    | HuksTagType.HUKS_TAG_TYPE_UINT \| 6      | Cipher mode.                   |
| HUKS_TAG_KEY_TYPE                      | HuksTagType.HUKS_TAG_TYPE_UINT \| 7      | Key type.                   |
| HUKS_TAG_ASSOCIATED_DATA               | HuksTagType.HUKS_TAG_TYPE_BYTES \| 8     | Associated authentication data.           |
| HUKS_TAG_NONCE                         | HuksTagType.HUKS_TAG_TYPE_BYTES \| 9     | Field for key encryption and decryption.                |
| HUKS_TAG_IV                            | HuksTagType.HUKS_TAG_TYPE_BYTES \| 10    | IV.                |
| HUKS_TAG_INFO                          | HuksTagType.HUKS_TAG_TYPE_BYTES \| 11    | Information generated during key derivation.                |
| HUKS_TAG_SALT                          | HuksTagType.HUKS_TAG_TYPE_BYTES \| 12    | Salt value used for key derivation.                |
| HUKS_TAG_PWD                           | HuksTagType.HUKS_TAG_TYPE_BYTES \| 13    | Password used for key derivation.            |
| HUKS_TAG_ITERATION                     | HuksTagType.HUKS_TAG_TYPE_UINT \| 14     | Number of iterations for key derivation.            |
| HUKS_TAG_KEY_GENERATE_TYPE             | HuksTagType.HUKS_TAG_TYPE_UINT \| 15     | Key generation type.               |
| HUKS_TAG_DERIVE_MAIN_KEY               | HuksTagType.HUKS_TAG_TYPE_BYTES \| 16    | Main key for key derivation.              |
| HUKS_TAG_DERIVE_FACTOR                 | HuksTagType.HUKS_TAG_TYPE_BYTES \| 17    | Factor for key derivation.            |
| HUKS_TAG_DERIVE_ALG                    | HuksTagType.HUKS_TAG_TYPE_UINT \| 18     | Type of the algorithm used for key derivation.            |
| HUKS_TAG_AGREE_ALG                     | HuksTagType.HUKS_TAG_TYPE_UINT \| 19     | Type of the algorithm used in key agreement.            |
| HUKS_TAG_AGREE_PUBLIC_KEY_IS_KEY_ALIAS | HuksTagType.HUKS_TAG_TYPE_BOOL \| 20     | Alias of the public key during key agreement.            |
| HUKS_TAG_AGREE_PRIVATE_KEY_ALIAS       | HuksTagType.HUKS_TAG_TYPE_BYTES \| 21    | Private key alias used in key agreement.            |
| HUKS_TAG_AGREE_PUBLIC_KEY              | HuksTagType.HUKS_TAG_TYPE_BYTES \| 22    | Public key used in key agreement.                |
| HUKS_TAG_KEY_ALIAS                     | HuksTagType.HUKS_TAG_TYPE_BYTES \| 23    | Key alias.                        |
| HUKS_TAG_DERIVE_KEY_SIZE               | HuksTagType.HUKS_TAG_TYPE_UINT \| 24     | Size of the derived key.                  |
| HUKS_TAG_ACTIVE_DATETIME               | HuksTagType.HUKS_TAG_TYPE_ULONG \| 201   | Reserved.                                |
| HUKS_TAG_ORIGINATION_EXPIRE_DATETIME   | HuksTagType.HUKS_TAG_TYPE_ULONG \| 202   | Reserved.                                |
| HUKS_TAG_USAGE_EXPIRE_DATETIME         | HuksTagType.HUKS_TAG_TYPE_ULONG \| 203   | Reserved.                                |
| HUKS_TAG_CREATION_DATETIME             | HuksTagType.HUKS_TAG_TYPE_ULONG \| 204   | Reserved.                                |
| HUKS_TAG_ALL_USERS                     | ksTagType.HUKS_TAG_TYPE_BOOL \| 301      | Reserved.                                |
| HUKS_TAG_USER_ID                       | HuksTagType.HUKS_TAG_TYPE_UINT \| 302    | Reserved.                                |
| HUKS_TAG_NO_AUTH_REQUIRED              | HuksTagType.HUKS_TAG_TYPE_BOOL \| 303    | Reserved.                                |
| HUKS_TAG_USER_AUTH_TYPE                | HuksTagType.HUKS_TAG_TYPE_UINT \| 304    | Reserved.                                |
| HUKS_TAG_AUTH_TIMEOUT                  | HuksTagType.HUKS_TAG_TYPE_UINT \| 305    | Reserved.                                |
| HUKS_TAG_AUTH_TOKEN                    | HuksTagType.HUKS_TAG_TYPE_BYTES \| 306   | Reserved.                                |
| HUKS_TAG_ATTESTATION_CHALLENGE         | HuksTagType.HUKS_TAG_TYPE_BYTES \| 501   | Challenge value used in the attestation.           |
| HUKS_TAG_ATTESTATION_APPLICATION_ID    | HuksTagType.HUKS_TAG_TYPE_BYTES \| 502   | Application ID used in the attestation.   |
| HUKS_TAG_ATTESTATION_ID_BRAND          | HuksTagType.HUKS_TAG_TYPE_BYTES \| 503   | Device brand.                     |
| HUKS_TAG_ATTESTATION_ID_DEVICE         | HuksTagType.HUKS_TAG_TYPE_BYTES \| 504   | Device.                    |
| HUKS_TAG_ATTESTATION_ID_PRODUCT        | HuksTagType.HUKS_TAG_TYPE_BYTES \| 505   | Product.                   |
| HUKS_TAG_ATTESTATION_ID_SERIAL         | HuksTagType.HUKS_TAG_TYPE_BYTES \| 506   | Device SN.                      |
| HUKS_TAG_ATTESTATION_ID_IMEI           | HuksTagType.HUKS_TAG_TYPE_BYTES \| 507   | Device IMEI.                    |
| HUKS_TAG_ATTESTATION_ID_MEID           | HuksTagType.HUKS_TAG_TYPE_BYTES \| 508   | Device MEID.                    |
| HUKS_TAG_ATTESTATION_ID_MANUFACTURER   | HuksTagType.HUKS_TAG_TYPE_BYTES \| 509   | Device manufacturer.                    |
| HUKS_TAG_ATTESTATION_ID_MODEL          | HuksTagType.HUKS_TAG_TYPE_BYTES \| 510   | Device model.                      |
| HUKS_TAG_ATTESTATION_ID_ALIAS          | HuksTagType.HUKS_TAG_TYPE_BYTES \| 511   | Key alias used in the attestation.         |
| HUKS_TAG_ATTESTATION_ID_SOCID          | HuksTagType.HUKS_TAG_TYPE_BYTES \| 512   | Device SOCID.                     |
| HUKS_TAG_ATTESTATION_ID_UDID           | HuksTagType.HUKS_TAG_TYPE_BYTES \| 513   | Device UDID.                      |
| HUKS_TAG_ATTESTATION_ID_SEC_LEVEL_INFO | HuksTagType.HUKS_TAG_TYPE_BYTES \| 514   | Security credential used for the attestation.         |
| HUKS_TAG_ATTESTATION_ID_VERSION_INFO   | HuksTagType.HUKS_TAG_TYPE_BYTES \| 515   | Version information used in the attestation.           |
| HUKS_TAG_IS_KEY_ALIAS                  | HuksTagType.HUKS_TAG_TYPE_BOOL \| 1001   | Whether to use the alias passed in during key generation. |
| HUKS_TAG_KEY_STORAGE_FLAG              | HuksTagType.HUKS_TAG_TYPE_UINT \| 1002   | Key storage mode.               |
| HUKS_TAG_IS_ALLOWED_WRAP               | HuksTagType.HUKS_TAG_TYPE_BOOL \| 1003   | Reserved.                                |
| HUKS_TAG_KEY_WRAP_TYPE                 | HuksTagType.HUKS_TAG_TYPE_UINT \| 1004   | Reserved.                                |
| HUKS_TAG_KEY_AUTH_ID                   | HuksTagType.HUKS_TAG_TYPE_BYTES \| 1005  | Reserved.                                |
| HUKS_TAG_KEY_ROLE                      | HuksTagType.HUKS_TAG_TYPE_UINT \| 1006   | Reserved.                                |
| HUKS_TAG_KEY_FLAG                      | HuksTagType.HUKS_TAG_TYPE_UINT \| 1007   | Flag of the key.                   |
| HUKS_TAG_IS_ASYNCHRONIZED              | HuksTagType.HUKS_TAG_TYPE_UINT \| 1008   | Reserved.                                |
| HUKS_TAG_SECURE_KEY_ALIAS              | HuksTagType.HUKS_TAG_TYPE_BOOL \| 1009   | Reserved.                                |
| HUKS_TAG_SECURE_KEY_UUID               | HuksTagType.HUKS_TAG_TYPE_BYTES \| 1010  | Reserved.                                |
| HUKS_TAG_KEY_DOMAIN                    | HuksTagType.HUKS_TAG_TYPE_UINT \| 1011   | Reserved.                                |
| HUKS_TAG_PROCESS_NAME                  | HuksTagType.HUKS_TAG_TYPE_BYTES \| 10001 | Process name.                   |
| HUKS_TAG_PACKAGE_NAME                  | HuksTagType.HUKS_TAG_TYPE_BYTES \| 10002 | Reserved.                                |
| HUKS_TAG_ACCESS_TIME                   | HuksTagType.HUKS_TAG_TYPE_UINT \| 10003  | Reserved.                                |
| HUKS_TAG_USES_TIME                     | HuksTagType.HUKS_TAG_TYPE_UINT \| 10004  | Reserved.                                |
| HUKS_TAG_CRYPTO_CTX                    | HuksTagType.HUKS_TAG_TYPE_ULONG \| 10005 | Reserved.                                |
| HUKS_TAG_KEY                           | HuksTagType.HUKS_TAG_TYPE_BYTES \| 10006 | Reserved.                                |
| HUKS_TAG_KEY_VERSION                   | HuksTagType.HUKS_TAG_TYPE_UINT \| 10007  | Key version.                   |
| HUKS_TAG_PAYLOAD_LEN                   | HuksTagType.HUKS_TAG_TYPE_UINT \| 10008  | Reserved.                                |
| HUKS_TAG_AE_TAG                        | HuksTagType.HUKS_TAG_TYPE_BYTES \| 10009 | Reserved.                                |
| HUKS_TAG_IS_KEY_HANDLE                 | HuksTagType.HUKS_TAG_TYPE_ULONG \| 10010 | Reserved.                                |
| HUKS_TAG_OS_VERSION                    | HuksTagType.HUKS_TAG_TYPE_UINT \| 10101  | OS version.               |
| HUKS_TAG_OS_PATCHLEVEL                 | HuksTagType.HUKS_TAG_TYPE_UINT \| 10102  | OS patch level.           |
| HUKS_TAG_SYMMETRIC_KEY_DATA            | HuksTagType.HUKS_TAG_TYPE_BYTES \| 20001 | Reserved.                                |
| HUKS_TAG_ASYMMETRIC_PUBLIC_KEY_DATA    | HuksTagType.HUKS_TAG_TYPE_BYTES \| 20002 | Reserved.                                |
| HUKS_TAG_ASYMMETRIC_PRIVATE_KEY_DATA   | HuksTagType.HUKS_TAG_TYPE_BYTES \| 20003 | Reserved.                                |

## huks.generateKey

generateKey(keyAlias: string, options: HuksOptions, callback: AsyncCallback\<HuksResult>) : void

Generates a key. This API uses an asynchronous callback to return the result.

**System capability**: SystemCapability.Security.Huks

**Parameters**

| Name  | Type                                     | Mandatory| Description                                                        |
| -------- | ----------------------------------------- | ---- | ------------------------------------------------------------ |
| keyAlias | string                                    | Yes  | Alias of the key.                                                       |
| options  | [HuksOptions](#huksoptions)               | Yes  | Tags required for generating the key.                                    |
| callback | AsyncCallback\<[HuksResult](#huksresult)> | Yes  | Callback used to return the result. If the operation is successful, **HUKS_SUCCESS** will be returned. If the operation fails, an error code defined in **HuksResult** will be returned. |

**Example**

```js
/* Generate an RSA key of 512 bits. */
var keyAlias = 'keyAlias';
var properties = new Array();
properties[0] = {
  tag: huks.HuksTag.HUKS_TAG_ALGORITHM,
  value: huks.HuksKeyAlg.HUKS_ALG_RSA
};
properties[1] = {
  tag: huks.HuksTag.HUKS_TAG_KEY_SIZE,
  value: huks.HuksKeySize.HUKS_RSA_KEY_SIZE_512
};
properties[2] = {
  tag: huks.HuksTag.HUKS_TAG_PURPOSE,
  value:
huks.HuksKeyPurpose.HUKS_KEY_PURPOSE_ENCRYPT |
huks.HuksKeyPurpose.HUKS_KEY_PURPOSE_DECRYPT
};
properties[3] = {
  tag: huks.HuksTag.HUKS_TAG_PADDING,
  value: huks.HuksKeyPadding.HUKS_PADDING_OAEP
};
properties[4] = {
  tag: huks.HuksTag.HUKS_TAG_DIGEST,
  value: huks.HuksKeyDigest.HUKS_DIGEST_SHA256
};
var options = {
  properties: properties
};
huks.generateKey(keyAlias, options, function (err, data){}); 
```

## huks.generateKey

generateKey(keyAlias: string, options: HuksOptions) : Promise\<HuksResult>

Generates a key. This API uses a promise to return the result.

**System capability**: SystemCapability.Security.Huks

**Parameters**

| Name  | Type                       | Mandatory| Description                    |
| -------- | --------------------------- | ---- | ------------------------ |
| keyAlias | string                      | Yes  | Alias of the key.              |
| options  | [HuksOptions](#huksoptions) | Yes  | Tags required for generating the key. |

**Return value**

| Type                               | Description                                              |
| ----------------------------------- | -------------------------------------------------- |
| Promise\<[HuksResult](#huksresult)> | Promise used to return the result. If the operation is successful, **HUKS_SUCCESS** will be returned. If the operation fails, an error code will be returned. |

**Example**

```js
/* Generate an ECC key of 256 bits. */
var keyAlias = 'keyAlias';
var properties = new Array();
properties[0] = {
  tag: huks.HuksTag.HUKS_TAG_ALGORITHM,
  value: huks.HuksKeyAlg.HUKS_ALG_ECC
};
properties[1] = {
  tag: huks.HuksTag.HUKS_TAG_KEY_SIZE,
  value: huks.HuksKeySize.HUKS_ECC_KEY_SIZE_256
};
properties[2] = {
  tag: huks.HuksTag.HUKS_TAG_PURPOSE,
  value:
huks.HuksKeyPurpose.HUKS_KEY_PURPOSE_SIGN |
huks.HuksKeyPurpose.HUKS_KEY_PURPOSE_VERIFY
};
properties[3] = {
  tag: huks.HuksTag.HUKS_TAG_DIGEST,
  value: huks.HuksKeyDigest.HUKS_DIGEST_SHA256
};
var options = {
  properties: properties
};
var result = huks.generateKey(keyAlias, options);
```

## huks.deleteKey

deleteKey(keyAlias: string, options: HuksOptions, callback: AsyncCallback\<HuksResult>) : void

Deletes a key. This API uses an asynchronous callback to return the result.

**System capability**: SystemCapability.Security.Huks

**Parameters**

| Name  | Type                                     | Mandatory| Description                                              |
| -------- | ----------------------------------------- | ---- | -------------------------------------------------- |
| keyAlias | string                                    | Yes  | Key alias passed in when the key was generated.               |
| options  | [HuksOptions](#huksoptions)               | Yes  | Empty object (leave this parameter empty).                          |
| callback | AsyncCallback\<[HuksResult](#huksresult)> | Yes  | Callback used to return the result. If the operation is successful, **HUKS_SUCCESS** will be returned. If the operation fails, an error code will be returned. |

**Example**

```js
/* Set options to emptyOptions. */
var keyAlias = 'keyAlias';
var emptyOptions = {
  properties: []
};
huks.deleteKey(keyAlias, emptyOptions, function (err, data) {});
```

## huks.deleteKey

deleteKey(keyAlias: string, options: HuksOptions) : Promise\<HuksResult>

Deletes a key. This API uses a promise to return the result.

**System capability**: SystemCapability.Security.Huks

**Parameters**

| Name  | Type       | Mandatory| Description                                                 |
| -------- | ----------- | ---- | ----------------------------------------------------- |
| keyAlias | string      | Yes  | Key alias passed in when the key was generated. |
| options | [HuksOptions](#huksoptions) | Yes  | Empty object (leave this parameter empty). |

**Return value**

| Type                               | Description                                              |
| ----------------------------------- | -------------------------------------------------- |
| Promise\<[HuksResult](#huksresult)> | Promise used to return the result. If the operation is successful, **HUKS_SUCCESS** will be returned. If the operation fails, an error code will be returned. |

**Example**

```js
/* Set options to emptyOptions. */
var keyAlias = 'keyAlias';
var emptyOptions = {
  properties: []
};
var result = huks.deleteKey(keyAlias, emptyOptions);
```

## huks.getSdkVersion

getSdkVersion(options: HuksOptions) : string

Obtains the SDK version of the current system.

**System capability**: SystemCapability.Security.Huks

**Parameters**

| Name | Type      | Mandatory| Description                     |
| ------- | ---------- | ---- | ------------------------- |
| options | [HuksOptions](#huksoptions) | Yes  | Empty object, which is used to hold the SDK version. |

**Return value**

| Type  | Description         |
| ------ | ------------- |
| string | SDK version obtained. |

**Example**

```js
/* Set options to emptyOptions. */
var emptyOptions = {
  properties: []
};
var result = huks.getSdkVersion(emptyOptions);
```

## huks.importKey

importKey(keyAlias: string, options: HuksOptions, callback: AsyncCallback\<HuksResult>) : void

Imports a key. This API uses an asynchronous callback to return the result.

**System capability**: SystemCapability.Security.Huks

**Parameters**

| Name  | Type                    | Mandatory| Description                                             |
| -------- | ------------------------ | ---- | ------------------------------------------------- |
| keyAlias | string                   | Yes  | Key alias, which is used to hold the key pair. |
| options  | [HuksOptions](#huksoptions) | Yes  | Tags required for the import and key pair to import. |
| callback | AsyncCallback\<[HuksResult](#huksresult)> | Yes  | Callback used to return the result. If the operation is successful, **HUKS_SUCCESS** will be returned. If the operation fails, an error code will be returned. |

**Example**

```js
/* Import an AES key of 256 bits. */
var plainTextSize32 = makeRandomArr(32);
function makeRandomArr(size) {
    var arr = new Uint8Array(size);
    for (var i = 0; i < size; i++) {
        arr[i] = Math.floor(Math.random() * 10);
    }
    return arr;
};
var keyAlias = 'keyAlias';
var properties = new Array();
properties[0] = {
  tag: huks.HuksTag.HUKS_TAG_ALGORITHM,
  value: huks.HuksKeyAlg.HUKS_ALG_AES
};
properties[1] = {
  tag: huks.HuksTag.HUKS_TAG_KEY_SIZE,
  value: huks.HuksKeySize.HUKS_AES_KEY_SIZE_256
};
properties[2] = {
  tag: huks.HuksTag.HUKS_TAG_PURPOSE,
  value:
huks.HuksKeyPurpose.HUKS_KEY_PURPOSE_ENCRYPT | huks.HuksKeyPurpose.HUKS_KEY_PURPOSE_DECRYPT
};
properties[3] = {
  tag: huks.HuksTag.HUKS_TAG_PADDING,
  value:huks.HuksKeyPadding.HUKS_PADDING_PKCS7
};
properties[4] = {
  tag: huks.HuksTag.HUKS_TAG_BLOCK_MODE,
  value: huks.HuksCipherMode.HUKS_MODE_ECB
};
var options = {
  properties: properties,
  inData: plainTextSize32
};
huks.importKey(keyAlias, options, function (err, data){});
```

## huks.importKey

importKey(keyAlias: string, options: HuksOptions) : Promise\<HuksResult>

Imports a key. This API uses a promise to return the result.

**System capability**: SystemCapability.Security.Huks

**Parameters**

| Name  | Type       | Mandatory| Description                                |
| -------- | ----------- | ---- | ------------------------------------ |
| keyAlias | string      | Yes  | Key alias, which is used to hold the key pair. |
| options  | [HuksOptions](#huksoptions) | Yes  | Tags required for the import and key pair to import. |

**Return value**

| Type                               | Description                                              |
| ----------------------------------- | -------------------------------------------------- |
| Promise\<[HuksResult](#huksresult)> | Promise used to return the result. If the operation is successful, **HUKS_SUCCESS** will be returned. If the operation fails, an error code will be returned. |

**Example**

```js
/* Import an AES key of 128 bits. */
var plainTextSize32 = makeRandomArr(32);

function makeRandomArr(size) {
    var arr = new Uint8Array(size);
    for (var i = 0; i < size; i++) {
        arr[i] = Math.floor(Math.random() * 10);
    }
    return arr;
};

/* Step 1 Generate a key. */
var keyAlias = 'keyAlias';
var properties = new Array();
properties[0] = {
  tag: huks.HuksTag.HUKS_TAG_ALGORITHM,
  value: huks.HuksKeyAlg.HUKS_ALG_AES
};
properties[1] = {
  tag: huks.HuksTag.HUKS_TAG_KEY_SIZE,
  value: huks.HuksKeySize.HUKS_AES_KEY_SIZE_128
};
properties[2] = {
  tag: huks.HuksTag.HUKS_TAG_PURPOSE,
  value: huks.HuksKeyPurpose.HUKS_KEY_PURPOSE_ENCRYPT | huks.HuksKeyPurpose.HUKS_KEY_PURPOSE_DECRYPT
};
properties[3] = {
  tag: huks.HuksTag.HUKS_TAG_PADDING,
  value:huks.HuksKeyPadding.HUKS_PADDING_PKCS7
};
properties[4] = {
  tag: huks.HuksTag.HUKS_TAG_BLOCK_MODE,
  value: huks.HuksCipherMode.HUKS_MODE_ECB
};
var huksoptions = {
  properties: properties,
  inData: plainTextSize32
};
var result = huks.importKey(keyAlias, huksoptions);
```

## huks.exportKey

exportKey(keyAlias: string, options: HuksOptions, callback: AsyncCallback\<HuksResult>) : void

Exports a key. This API uses an asynchronous callback to return the result.

**System capability**: SystemCapability.Security.Huks

**Parameters**

| Name  | Type                                     | Mandatory| Description                                                        |
| -------- | ----------------------------------------- | ---- | ------------------------------------------------------------ |
| keyAlias | string                                    | Yes  | Key alias, which must be the same as the alias used when the key was generated.                |
| options  | [HuksOptions](#huksoptions)               | Yes  | Empty object (leave this parameter empty).                                    |
| callback | AsyncCallback\<[HuksResult](#huksresult)> | Yes  | Callback used to return the result. If the operation is successful, **HUKS_SUCCESS** will be returned. If the operation fails, an error code will be returned. **outData** contains the public key exported. |

**Example**

```js
/* Set options to emptyOptions. */
var keyAlias = 'keyAlias';
var emptyOptions = {
  properties: []
};
huks.exportKey(keyAlias, emptyOptions, function (err, data){});
```

## huks.exportKey

exportKey(keyAlias: string, options: HuksOptions) : Promise\<HuksResult>

Exports a key. This API uses a promise to return the result.

**System capability**: SystemCapability.Security.Huks

**Parameters**

| Name  | Type       | Mandatory| Description                                                        |
| -------- | ----------- | ---- | ------------------------------------------------------------ |
| keyAlias | string      | Yes  | Key alias, which must be the same as the alias used when the key was generated. |
| options  | [HuksOptions](#huksoptions) | Yes  | Empty object (leave this parameter empty). |

**Return value**

| Type                               | Description                                                        |
| ----------------------------------- | ------------------------------------------------------------ |
| Promise\<[HuksResult](#huksresult)> | Promise used to return the result. If the operation is successful, **HUKS_SUCCESS** will be returned. If the operation fails, an error code will be returned. **outData** contains the public key exported. |

**Example**

```js
/* Set options to emptyOptions. */
var keyAlias = 'keyAlias';
var emptyOptions = {
  properties: []
};
var result = huks.exportKey(keyAlias, emptyOptions);
```

## huks.getKeyProperties

getKeyProperties(keyAlias: string, options: HuksOptions, callback: AsyncCallback\<HuksResult>) : void

Obtains key properties. This API uses an asynchronous callback to return the result.

**System capability**: SystemCapability.Security.Huks

**Parameters**

| Name  | Type                                     | Mandatory| Description                                                        |
| -------- | ----------------------------------------- | ---- | ------------------------------------------------------------ |
| keyAlias | string                                    | Yes  | Key alias, which must be the same as the alias used when the key was generated.                |
| options  | [HuksOptions](#huksoptions)               | Yes  | Empty object (leave this parameter empty).                                    |
| callback | AsyncCallback\<[HuksResult](#huksresult)> | Yes  | Callback used to return the result. **HUKS_SUCCESS** will be returned if the operation is successful; an error code will be returned otherwise. |

**Example**

```js
/* Set options to emptyOptions. */
var keyAlias = 'keyAlias';
var emptyOptions = {
  properties: []
};
huks.getKeyProperties(keyAlias, emptyOptions, function (err, data){});
```

## huks.getKeyProperties

getKeyProperties(keyAlias: string, options: HuksOptions) : Promise\<HuksResult>

Obtains key properties. This API uses a promise to return the result.

**System capability**: SystemCapability.Security.Huks

**Parameters**

| Name  | Type       | Mandatory| Description                                                        |
| -------- | ----------- | ---- | ------------------------------------------------------------ |
| keyAlias | string      | Yes  | Key alias, which must be the same as the alias used when the key was generated. |
| options  | [HuksOptions](#huksoptions) | Yes  | Empty object (leave this parameter empty). |

**Return value**

| Type              | Description                                                        |
| ------------------ | ------------------------------------------------------------ |
| Promise\<[HuksResult](#huksoptions)> | Promise used to return the result. In the return result, **HUKS_SUCCESS** will be returned for **errorCode** if the operation is successful; an error code will be returned otherwise. **properties** returns the parameters required for generating the key. |

**Example**

```js
/* Set options to emptyOptions. */
var keyAlias = 'keyAlias';
var emptyOptions = {
  properties: []
};
var result = huks.getKeyProperties(keyAlias, emptyOptions);
```

## huks.isKeyExist

isKeyExist(keyAlias: string, options: HuksOptions, callback: AsyncCallback\<boolean>) : void

Checks whether a key exists. This API uses an asynchronous callback to return the result.

**System capability**: SystemCapability.Security.Huks

**Parameters**

| Name  | Type                  | Mandatory| Description                                 |
| -------- | ---------------------- | ---- | ------------------------------------- |
| keyAlias | string                 | Yes  | Alias of the key to check. |
| options  | [HuksOptions](#huksoptions) | Yes  | Empty object (leave this parameter empty). |
| callback | AsyncCallback\<boolean> | Yes  | Callback used to return the result. **TRUE** means that the key exists; **FALSE** means the opposite. |

**Example**

```js
/* Set options to emptyOptions. */
var keyAlias = 'keyAlias';
var emptyOptions = {
  properties: []
};
huks.isKeyExist(keyAlias, emptyOptions, function (err, data){});
```

## huks.isKeyExist

isKeyExist(keyAlias: string, options: HuksOptions) : Promise\<boolean>

Checks whether a key exists. This API uses a promise to return the result.

**System capability**: SystemCapability.Security.Huks

**Parameters**

| Name  | Type       | Mandatory| Description                            |
| -------- | ----------- | ---- | -------------------------------- |
| keyAlias | string      | Yes  | Alias of the key to check. |
| options  | [HuksOptions](#huksoptions) | Yes  | Empty object (leave this parameter empty). |

**Return value**

| Type             | Description                                   |
| ----------------- | --------------------------------------- |
| Promise\<boolean> | Promise used to return the result. **TRUE** means that the key exists; **FALSE** means the opposite. |

**Example**

```js
/* Set options to emptyOptions. */
var keyAlias = 'keyAlias';
var emptyOptions = {
  properties: []
};
var result = huks.isKeyExist(keyAlias, emptyOptions);
```



## huks.init

init(keyAlias: string, options: HuksOptions, callback: AsyncCallback\<HuksHandle>) : void

Initializes a key. This API uses an asynchronous callback to return the result.

**System capability**: SystemCapability.Security.Huks

**Parameters**

| Name  | Type                  | Mandatory| Description                                 |
| -------- | ---------------------- | ---- | ------------------------------------- |
| keyAlias | string                 | Yes  | Alias of the target key. |
| options  | [HuksOptions](#huksoptions) | Yes  | Parameters used for initialization. |
| callback | AsyncCallback\<[HuksHandle](#hukshandle)> | Yes  | Callback used to return the handle of the initialization operation. |


## huks.init

init(keyAlias: string, options: HuksOptions) : Promise\<HuksHandle>

Initializes a key. This API uses a promise to return the result.

**System capability**: SystemCapability.Security.Huks

**Parameters**

| Name  | Type                  | Mandatory| Description                                 |
| -------- | ---------------------- | ---- | ------------------------------------- |
| keyAlias | string                 | Yes  | Alias of the target key. |
| options  | [HuksOptions](#huksoptions) | Yes  | Parameters used for initialization. |
| promise | Promise\<[HuksHandle](#hukshandle)> | Yes  | Promise used to return the handle of the initialization operation. |


## huks.update

update(handle: number, token?: Uint8Array, options: HuksOptions, callback: AsyncCallback\<HuksResult>) : void

Updates a key. This API uses an asynchronous callback to return the result.

**System capability**: SystemCapability.Security.Huks

**Parameters**

| Name  | Type                  | Mandatory| Description                                 |
| -------- | ---------------------- | ---- | ------------------------------------- |
| handle | number           | Yes  | Handle of the **Update** operation. |
| token | Uint8Array | No| Token of the **Update** operation. |
| options  | [HuksOptions](#huksoptions) | Yes  | Parameters of the **Update** operation. |
| callback | AsyncCallback\<[HuksResult](#huksresult)> | Yes| Callback used to return the operation result. |


## huks.update

update(handle: number, token?: Uint8Array, options: HuksOptions) : Promise\<HuksResult>

Updates a key. This API uses a promise to return the result.

**System capability**: SystemCapability.Security.Huks

**Parameters**

| Name  | Type                  | Mandatory| Description                                 |
| -------- | ---------------------- | ---- | ------------------------------------- |
| handle | number           | Yes  | Handle of the **Update** operation. |
| token | Uint8Array | No| Token of the **Update** operation. |
| options  | [HuksOptions](#huksoptions) | Yes  | Parameters of the **Update** operation. |
| promise | Promise\<[HuksResult](#huksresult)> | Yes| Promise used to return the operation result. |


## huks.finish

finish(handle: number, options: HuksOptions, callback: AsyncCallback\<HuksResult>) : void

Completes the key operation and releases resources. This API uses an asynchronous callback to return the result.

**System capability**: SystemCapability.Security.Huks

**Parameters**

| Name  | Type                  | Mandatory| Description                                 |
| -------- | ---------------------- | ---- | ------------------------------------- |
| handle | number           | Yes  | Handle of the **Finish** operation. |
| options  | [HuksOptions](#huksoptions) | Yes  | Parameters of the **Finish** operation. |
| callback | AsyncCallback\<[HuksResult](#huksresult)> | Yes| Callback used to return the operation result. |


## huks.finish

finish(handle: number, options: HuksOptions) : Promise\<HuksResult>

Completes the key operation and releases resources. This API uses a promise to return the result.

**System capability**: SystemCapability.Security.Huks

**Parameters**

| Name  | Type                  | Mandatory| Description                                 |
| -------- | ---------------------- | ---- | ------------------------------------- |
| handle | number           | Yes  | Handle of the **Finish** operation. |
| options  | [HuksOptions](#huksoptions) | Yes  | Parameters of the **Finish** operation. |
| promise | Promise\<[HuksResult](#HuksResult)> | Yes| Promise used to return the operation result. |


## huks.abort

abort(handle: number, options: HuksOptions, callback: AsyncCallback\<HuksResult>) : void

Aborts the use of the key. This API uses an asynchronous callback to return the result.

**System capability**: SystemCapability.Security.Huks

**Parameters**

| Name  | Type                  | Mandatory| Description                                 |
| -------- | ---------------------- | ---- | ------------------------------------- |
| handle | number           | Yes  | Handle of the **Abort** operation. |
| options  | [HuksOptions](#huksoptions) | Yes  | Parameters of the **Abort** operation. |
| callback | AsyncCallback\<[HuksResult](#huksresult)> | Yes| Callback used to return the operation result. |

**Example**

```js
/* huks.init, huks.update, and huks.finish must be used together.
 * If an error occurs in any of them, huks.abort must be called to terminate the use of the key.
 *
 * The following uses the callback of an RSA 1024-bit key as an example.
 */
import router from '@system.router';
import huks from '@ohos.security.huks';

async function routePage() {
  let options = {
    uri: 'pages/second'
  }
  try {
    await router.push(options)
  } catch (err) {
    console.error(`fail callback, code: ${err.code}, msg: ${err.msg}`)
  }
}
var keyalias = "HuksDemoRSA";
var properties = new Array();
var options = {
  properties: properties,
  inData: new Uint8Array(0)
};
var handle;
var resultMessage = "";
async function generateKey() {
  properties[0] = {
    tag: huks.HuksTag.HUKS_TAG_ALGORITHM,
    value: huks.HuksKeyAlg.HUKS_ALG_RSA
  };
  properties[1] = {
    tag: huks.HuksTag.HUKS_TAG_KEY_SIZE,
    value: huks.HuksKeySize.HUKS_RSA_KEY_SIZE_1024
  };
  properties[2] = {
    tag: huks.HuksTag.HUKS_TAG_PURPOSE,
    value: huks.HuksKeyPurpose.HUKS_KEY_PURPOSE_ENCRYPT
  };
  properties[3] = {
    tag: huks.HuksTag.HUKS_TAG_PADDING,
    value: huks.HuksKeyPadding.HUKS_PADDING_OAEP
  };
  properties[4] = {
    tag: huks.HuksTag.HUKS_TAG_DIGEST,
    value: huks.HuksKeyDigest.HUKS_DIGEST_SHA256
  };
  huks.generateKey(keyalias, options);
}
function stringToUint8Array(str) {
  var arr = [];
  for (var i = 0, j = str.length; i < j; ++i) {
    arr.push(str.charCodeAt(i));
  }
  var tmpUint8Array = new Uint8Array(arr);
  return tmpUint8Array;
}
async function huksInit() {
  await huks.init(keyalias, options).then((data) => {
    console.log(`test init data: ${JSON.stringify(data)}`);
    handle = data.handle;
  }).catch((err) => {
    console.log("test init err information: " + JSON.stringify(err))
  })
}
async function huksUpdate() {
    options.inData = stringToUint8Array("huksHmacTest");
    await huks.update(handle, options).then((data) => {
      if (data.errorCode === 0) {
        resultMessage += "update success!";
      } else {
        resultMessage += "update fail!";
      }
    });
    console.log(resultMessage);
}
function huksFinish() {
  options.inData = stringToUint8Array("HuksDemoHMAC");
  huks.finish(handle, options).then((data) => {
    if (data.errorCode === 0) {
      resultMessage = "finish success!";
    } else {
      resultMessage = "finish fail errorCode: " + data.errorCode;
    }
  }).catch((err) => {
    resultMessage = "Failed to complete the key operation. catch errorMessage:" + JSON.stringify(err)
  });
  console.log(resultMessage);
}
async function huksAbort() {
  huks.abort(handle, options).then((data) => {
    if (data.errorCode === 0) {
      resultMessage = "abort success!";
    } else {
      resultMessage = "abort fail errorCode: " + data.errorCode;
    }
  }).catch((err) => {
    resultMessage = "Failed to abort the use of the key. catch errorMessage:" + JSON.stringify(err)
  });
  console.log(resultMessage);
}

@Entry
@Component
struct Index {
  build() {
    Flex({ direction: FlexDirection.Column, alignItems: ItemAlign.Center, justifyContent: FlexAlign.Center }) {
      Text('Hello World')
        .fontSize(50)
        .fontWeight(FontWeight.Bold)
      Button() {
        Text('Tocallback')
          .fontSize(25)
          .fontWeight(FontWeight.Bold)
      }.type(ButtonType.Capsule)
      .margin({
        top: 20
      })
      .width('50%')
      .height('10%')
      .backgroundColor('#0D9FFB')
      .onClick(() => {
        routePage()
      })
      Button() {
        Text('generateKey')
          .fontSize(25)
          .fontWeight(FontWeight.Bold)
      }.type(ButtonType.Capsule)
      .margin({
        top: 20
      })
      .width('50%')
      .height('10%')
      .backgroundColor('#0D9FFB')
      .onClick(() => {
        generateKey()
      })
      Button() {
        Text('Init')
          .fontSize(25)
          .fontWeight(FontWeight.Bold)
      }.type(ButtonType.Capsule)
      .margin({
        top: 20
      })
      .width('50%')
      .height('10%')
      .backgroundColor('#0D9FFB')
      .onClick(() => {
        huksInit()
      })
      Button() {
        Text('Update')
          .fontSize(25)
          .fontWeight(FontWeight.Bold)
      }.type(ButtonType.Capsule)
      .margin({
        top: 20
      })
      .width('50%')
      .height('10%')
      .backgroundColor('#0D9FFB')
      .onClick(() => {
        huksUpdate()
      })
      Button() {
        Text('Finish')
          .fontSize(25)
          .fontWeight(FontWeight.Bold)
      }.type(ButtonType.Capsule)
      .margin({
        top: 20
      })
      .width('50%')
      .height('10%')
      .backgroundColor('#0D9FFB')
      .onClick(() => {
        huksFinish()
      })
      Button() {
        Text('Abort')
          .fontSize(25)
          .fontWeight(FontWeight.Bold)
      }.type(ButtonType.Capsule)
      .margin({
        top: 20
      })
      .width('50%')
      .height('10%')
      .backgroundColor('#0D9FFB')
      .onClick(() => {
        huksAbort()
      })
    }
    .width('100%')
    .height('100%')
  }
}
```

## huks.abort

abort(handle: number, options: HuksOptions) : Promise\<HuksResult>;

Aborts the use of the key. This API uses a promise to return the result.

**System capability**: SystemCapability.Security.Huks

**Parameters**

| Name  | Type                  | Mandatory| Description                                 |
| -------- | ---------------------- | ---- | ------------------------------------- |
| handle | number           | Yes  | Handle of the **Abort** operation. |
| options  | [HuksOptions](#huksoptions) | Yes  | Parameters of the **Abort** operation. |
| promise | Promise\<[HuksResult](#huksresult)> | Yes| Promise used to return the operation result. |

**Example**

```js
/* huks.init, huks.update, and huks.finish must be used together.
 * If an error occurs in any of them, huks.abort must be called to terminate the use of the key.
 *
 * The following uses the promise of an RSA 1024-bit key as an example.
 */
import router from '@system.router';
import huks from '@ohos.security.huks';

async function routePage() {
  let options = {
    uri: 'pages/second'
  }
  try {
    await router.push(options)
  } catch (err) {
    console.error(`fail callback, code: ${err.code}, msg: ${err.msg}`)
  }
}

var keyalias = "HuksDemoRSA";
var properties = new Array();
var options = {
  properties: properties,
  inData: new Uint8Array(0)
};
var handle;
var resultMessage = "";
function stringToUint8Array(str) {
  var arr = [];
  for (var i = 0, j = str.length; i < j; ++i) {
    arr.push(str.charCodeAt(i));
  }
  var tmpUint8Array = new Uint8Array(arr);
  return tmpUint8Array;
}

async function generateKey() {
  properties[0] = {
    tag: huks.HuksTag.HUKS_TAG_ALGORITHM,
    value: huks.HuksKeyAlg.HUKS_ALG_RSA
  };
  properties[1] = {
    tag: huks.HuksTag.HUKS_TAG_KEY_SIZE,
    value: huks.HuksKeySize.HUKS_RSA_KEY_SIZE_1024
  };
  properties[2] = {
    tag: huks.HuksTag.HUKS_TAG_PURPOSE,
    value: huks.HuksKeyPurpose.HUKS_KEY_PURPOSE_ENCRYPT
  };
  properties[3] = {
    tag: huks.HuksTag.HUKS_TAG_PADDING,
    value: huks.HuksKeyPadding.HUKS_PADDING_OAEP
  };
  properties[4] = {
    tag: huks.HuksTag.HUKS_TAG_DIGEST,
    value: huks.HuksKeyDigest.HUKS_DIGEST_SHA256
  };
  huks.generateKey(keyalias, options, function (err, data) { });
}
async function huksInit() {
  return new Promise((resolve, reject) => {
    huks.init(keyalias, options, async function (err, data) {
      if (data.errorCode === 0) {
        resultMessage = "Initialization successful!"
        handle = data.handle;
      } else {
        resultMessage = "init fail errorCode: " + data.errorCode
      }
    });
  });
}

async function huksUpdate() {
    options.inData = stringToUint8Array("huksHmacTest");
    new Promise((resolve, reject) => {
      huks.update(handle, options, function (err, data) {
        if (data.errorCode === 0) {
          resultMessage += "update success!";
        } else {
          resultMessage += "update fail!";
        }
      });
    });
    console.log(resultMessage);

}

async function huksFinish() {
  options.inData = stringToUint8Array("0");
  new Promise((resolve, reject) => {
    huks.finish(handle, options, function (err, data) {
      if (data.errorCode === 0) {
        resultMessage = "finish success!";
      } else {
        resultMessage =  "finish fail errorCode: " + data.errorCode;
      }
    });
  });
}

function huksAbort() {
  new Promise((resolve, reject) => {
    huks.abort(handle, options, function (err, data) {
      console.log(`Huks_Demo hmac huksAbort1 data ${JSON.stringify(data)}`);
      console.log(`Huks_Demo hmac huksAbort1 err ${JSON.stringify(err)}`);
    });
  });
}
@Entry
@Component
struct Index {
  build() {
    Flex({ direction: FlexDirection.Column, alignItems: ItemAlign.Center, justifyContent: FlexAlign.Center }) {
      Text('Hello World')
        .fontSize(50)
        .fontWeight(FontWeight.Bold)
      Button() {
        Text('to Promise')
          .fontSize(20)
          .fontWeight(FontWeight.Bold)
      }.type(ButtonType.Capsule)
      .margin({
        top: 20
      })
      .width('50%')
      .height('10%')
      .backgroundColor('#0D9FFB')
      .onClick(() => {
        router.back()
      })
      Button() {
        Text('generateKey')
          .fontSize(25)
          .fontWeight(FontWeight.Bold)
      }.type(ButtonType.Capsule)
      .margin({
        top: 20
      })
      .width('50%')
      .height('10%')
      .backgroundColor('#0D9FFB')
      .onClick(() => {
        generateKey()
      })
      Button() {
        Text('Init')
          .fontSize(25)
          .fontWeight(FontWeight.Bold)
      }.type(ButtonType.Capsule)
      .margin({
        top: 20
      })
      .width('50%')
      .height('10%')
      .backgroundColor('#0D9FFB')
      .onClick(() => {
        huksInit()
      })
      Button() {
        Text('Update')
          .fontSize(25)
          .fontWeight(FontWeight.Bold)
      }.type(ButtonType.Capsule)
      .margin({
        top: 20
      })
      .width('50%')
      .height('10%')
      .backgroundColor('#0D9FFB')
      .onClick(() => {
        huksUpdate()
      })
      Button() {
        Text('Finish')
          .fontSize(25)
          .fontWeight(FontWeight.Bold)
      }.type(ButtonType.Capsule)
      .margin({
        top: 20
      })
      .width('50%')
      .height('10%')
      .backgroundColor('#0D9FFB')
      .onClick(() => {
        huksFinish()
      })
      Button() {
        Text('Abort')
          .fontSize(25)
          .fontWeight(FontWeight.Bold)
      }.type(ButtonType.Capsule)
      .margin({
        top: 20
      })
      .width('50%')
      .height('10%')
      .backgroundColor('#0D9FFB')
      .onClick(() => {
        huksAbort()
      })
    }
    .width('100%')
    .height('100%')
  }
}
```

## HuksParam

Defines the **param** in the **properties** array of **options** used in the APIs.

**System capability**: SystemCapability.Security.Huks

| Name| Type                               | Mandatory| Description      |
| ------ | ----------------------------------- | ---- | ---------- |
| tag    | HuksTag                             | Yes  | Tag.      |
| value  | boolean\|number\|bigint\|Uint8Array | Yes  | Value of the tag. |

## HuksOptions

Defines the **options** used in the APIs. 

**System capability**: SystemCapability.Security.Huks

| Name    | Type             | Mandatory| Description                    |
| ---------- | ----------------- | ---- | ------------------------ |
| properties | Array\<HuksParam> | No  | Array used to hold **HuksParam**. |
| inData     | Uint8Array        | No  | Input data.              |

## HuksHandle

Defines the HUKS handle structure.

**System capability**: SystemCapability.Security.Huks

| Name    | Type            | Mandatory | Description    |
| ---------- | ---------------- | ---- | -------- |
| errorCode  | number           | Yes  | Error code. |
| handle    | number       | Yes| Value of the handle. |
| token | Uint8Array | No| Reserved. |


## HuksResult

Defines the **HuksResult** structure.

**System capability**: SystemCapability.Security.Huks



| Name    | Type             | Mandatory | Description    |
| ---------- | ----------------- | ---- | -------- |
| errorCode  | number            | Yes  | Error code.  |
| outData    | Uint8Array        | No  | Output data. |
| properties | Array\<HuksParam> | No  | Properties.    |
| certChains | Array\<string>    | No  | Certificate chain.  |
