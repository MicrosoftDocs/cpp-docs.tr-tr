---
description: 'Daha fazla bilgi edinin: CAtlTransactionManager sınıfı'
title: CAtlTransactionManager sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAtlTransactionManager
- ATLTRANSACTIONMANAGER/ATL::CAtlTransactionManager
- ATLTRANSACTIONMANAGER/ATL::Close
- ATLTRANSACTIONMANAGER/ATL::Commit
- ATLTRANSACTIONMANAGER/ATL::Create
- ATLTRANSACTIONMANAGER/ATL::CreateFile
- ATLTRANSACTIONMANAGER/ATL::DeleteFile
- ATLTRANSACTIONMANAGER/ATL::FindFirstFile
- ATLTRANSACTIONMANAGER/ATL::GetFileAttributes
- ATLTRANSACTIONMANAGER/ATL::GetFileAttributesEx
- ATLTRANSACTIONMANAGER/ATL::GetHandle
- ATLTRANSACTIONMANAGER/ATL::IsFallback
- ATLTRANSACTIONMANAGER/ATL::MoveFile
- ATLTRANSACTIONMANAGER/ATL::RegCreateKeyEx
- ATLTRANSACTIONMANAGER/ATL::RegDeleteKey
- ATLTRANSACTIONMANAGER/ATL::RegOpenKeyEx
- ATLTRANSACTIONMANAGER/ATL::Rollback
- ATLTRANSACTIONMANAGER/ATL::SetFileAttributes
- ATLTRANSACTIONMANAGER/ATL::m_bFallback
- ATLTRANSACTIONMANAGER/ATL::m_hTransaction
helpviewer_keywords:
- CAtlTransactionManager class
ms.assetid: b01732dc-1d16-4b42-bfac-b137fca2b740
ms.openlocfilehash: 25d5ea7e9b4838f483dd7f9ee408cdd5bd4c88cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147192"
---
# <a name="catltransactionmanager-class"></a>CAtlTransactionManager sınıfı

CAtlTransactionManager sınıfı, çekirdek Işlem yöneticisi (KTM) işlevlerine bir sarmalayıcı sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```cpp
class CAtlTransactionManager;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[~ CAtlTransactionManager](#dtor)|CAtlTransactionManager yok edici.|
|[CAtlTransactionManager](#catltransactionmanager)|CAtlTransactionManager Oluşturucusu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Kapat](#close)|İşlem tanıtıcısını kapatır.|
|[İşleme](#commit)|İşlemin yürütüldüğü istek.|
|[Oluştur](#create)|İşlem tanıtıcısını oluşturur.|
|[CreateFile](#createfile)|Bir dosya, dosya akışı veya dizini işlem temelli bir işlem olarak oluşturur veya açar.|
|[DeleteFile](#deletefile)|Var olan bir dosyayı işlenen işlem olarak siler.|
|[FindFirstFile](#findfirstfile)|Bir dosya veya alt dizinin dizinini işlenen işlem olarak arar.|
|[GetFileAttributes](#getfileattributes)|Belirtilen dosya veya dizinin dosya sistemi özniteliklerini işlem temelli bir işlem olarak alır.|
|[GetFileAttributesEx](#getfileattributesex)|Belirtilen dosya veya dizinin dosya sistemi özniteliklerini işlem temelli bir işlem olarak alır.|
|[GetHandle](#gethandle)|İşlem tanıtıcısını döndürür.|
|[Isgeri dönüş](#isfallback)|Geri dönüş çağrılarının etkinleştirilip etkinleştirilmeyeceğini belirler.|
|[MoveFile](#movefile)|Var olan bir dosyayı veya bir dizini, alt öğeleri de dahil olmak üzere işlem temelli bir işlem olarak kaydırır.|
|[RegCreateKeyEx](#regcreatekeyex)|Belirtilen kayıt defteri anahtarını oluşturur ve bir işlem ile ilişkilendirir. Anahtar zaten varsa, işlev onu açar.|
|[RegDeleteKey](#regdeletekey)|Bir alt anahtarı ve değerlerini, kayıt defterinin belirtilen platforma özgü görünümünden işlem temelli bir işlem olarak siler.|
|[RegOpenKeyEx](#regopenkeyex)|Belirtilen kayıt defteri anahtarını açar ve bir işlem ile ilişkilendirir.|
|[Geri alma](#rollback)|İşlemin geri alınmasına yönelik istekler.|
|[SetFileAttributes](#setfileattributes)|Bir dosya veya dizinin özniteliklerini işlem temelli bir işlem olarak ayarlar.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[m_bFallback](#m_bfallback)|Geri dönüş destekleniyorsa doğru; Aksi takdirde FALSE.|
|[m_hTransaction](#m_htransaction)|İşlem tanıtıcısı.|

## <a name="remarks"></a>Açıklamalar

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[ATL:: CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltransactionmanager. h

## <a name="catltransactionmanager"></a><a name="dtor"></a>  ~ CAtlTransactionManager

CAtlTransactionManager yok edici.

```cpp
virtual ~CAtlTransactionManager();
```

### <a name="remarks"></a>Açıklamalar

Normal işlemede, işlem otomatik olarak kaydedilir ve kapatılır. Bir özel durum bırakma sırasında yıkıcı çağrılırsa, işlem geri alınır ve kapatılır.

## <a name="catltransactionmanager"></a><a name="catltransactionmanager"></a> CAtlTransactionManager

CAtlTransactionManager Oluşturucusu.

```cpp
CAtlTransactionManager(BOOL bFallback = TRUE, BOOL bAutoCreateTransaction = TRUE);
```

### <a name="parameters"></a>Parametreler

*bFallback*<br/>
DOĞRU, destek geri dönüşü gösterir. İşlem temelli işlev başarısız olursa, sınıf otomatik olarak "işlem temelli olmayan" işlevini çağırır. FALSE, "Fallback" çağrılarının olmadığını gösterir.

*bAutoCreateTransaction*<br/>
TRUE, işlem işleyicisinin oluşturucuda otomatik olarak oluşturulduğunu gösterir. FALSE, olmadığını gösterir.

### <a name="remarks"></a>Açıklamalar

## <a name="close"></a><a name="close"></a> ~Eksik

İşlem tanıtıcısını kapatır.

```cpp
inline BOOL Close();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı işlevini çağırır `CloseHandle` . Yöntemi yıkıcıda otomatik olarak çağırılır.

## <a name="commit"></a><a name="commit"></a> Uygulayın

İşlemin yürütüldüğü istek.

```cpp
inline BOOL Commit();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı işlevini çağırır `CommitTransaction` . Yöntemi yıkıcıda otomatik olarak çağırılır.

## <a name="create"></a><a name="create"></a> Oluşturma

İşlem tanıtıcısını oluşturur.

```cpp
inline BOOL Create();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı işlevini çağırır `CreateTransaction` . Şunu denetleyin

## <a name="createfile"></a><a name="createfile"></a> CreateFile

Bir dosya, dosya akışı veya dizini işlem temelli bir işlem olarak oluşturur veya açar.

```cpp
inline HANDLE CreateFile(
    LPCTSTR lpFileName,
    DWORD dwDesiredAccess,
    DWORD dwShareMode,
    LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    DWORD dwCreationDisposition,
    DWORD dwFlagsAndAttributes,
    HANDLE hTemplateFile);
```

### <a name="parameters"></a>Parametreler

*lpFileName*<br/>
Oluşturulacak veya açılacak nesnenin adı.

*dwDesiredAccess*<br/>
Okuma, yazma, her ikisi veya hiçbiri (sıfır) olarak özetlenebilir nesnesine erişim. En sık kullanılan değerler GENERIC_READ, GENERIC_WRITE veya her ikisi: GENERIC_READ &#124; GENERIC_WRITE.

*dwShareMode*<br/>
Okuma, yazma, her ikisi, silme, tümü bu veya None olabilir: 0, FILE_SHARE_DELETE, FILE_SHARE_READ, FILE_SHARE_WRITE olabilen bir nesnenin Paylaşım modu.

*lpSecurityAttributes*<br/>
İsteğe bağlı güvenlik tanımlayıcısı içeren SECURITY_ATTRIBUTES yapısına yönelik bir işaretçi ve ayrıca döndürülen Tanıtıcının alt süreçler tarafından devralınıp alınmayacağını belirler. Parametre NULL olabilir.

*dwCreationDisposition*<br/>
Var olan ve olmayan dosyalarda gerçekleştirilecek bir eylem. Bu parametre, birleştirilemeyecek olan şu değerlerden biri olmalıdır: CREATE_ALWAYS, CREATE_NEW, OPEN_ALWAYS, OPEN_EXISTING veya TRUNCATE_EXISTING.

*dwFlagsAndAttributes*<br/>
Dosya öznitelikleri ve bayrakları. Bu parametre, kullanılabilir dosya özniteliklerinin herhangi bir birleşimini içerebilir (FILE_ATTRIBUTE_ *). Diğer tüm dosya özniteliklerinin FILE_ATTRIBUTE_NORMAL geçersiz kılar. Bu parametre Ayrıca \* , arabelleğe alma davranışı, erişim modları ve diğer özel amaçlı bayrakların denetimi için bayrakların (FILE_FLAG_) birleşimlerini de içerebilir. Bunlar FILE_ATTRIBUTE_ \* değerleriyle birleştirir.

*hTemplateFile*<br/>
GENERIC_READ erişim hakkına sahip bir şablon dosyası için geçerli bir tanıtıcı. Şablon dosyası, oluşturulmakta olan dosyanın dosya özniteliklerini ve genişletilmiş özniteliklerini sağlar. Bu parametre NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Nesneye erişmek için kullanılabilecek bir tanıtıcı döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı işlevini çağırır `CreateFileTransacted` .

## <a name="deletefile"></a><a name="deletefile"></a> DeleteFile

Var olan bir dosyayı işlenen işlem olarak siler.

```cpp
inline BOOL DeleteFile(LPCTSTR lpFileName);
```

### <a name="parameters"></a>Parametreler

*lpFileName*<br/>
Silinecek dosyanın adı.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı işlevini çağırır `DeleteFileTransacted` .

## <a name="findfirstfile"></a><a name="findfirstfile"></a> FindFirstFile

Bir dosya veya alt dizinin dizinini işlenen işlem olarak arar.

```cpp
inline HANDLE FindFirstFile(
    LPCTSTR lpFileName,
    WIN32_FIND_DATA* pNextInfo);
```

### <a name="parameters"></a>Parametreler

*lpFileName*<br/>
Aranacak dizin veya yol ve dosya adı. Bu parametre, yıldız işareti (*) veya soru işareti () gibi joker karakter içerebilir.

*Pnextınfo*<br/>
Bulunan bir dosya veya alt dizin hakkında bilgi alan WIN32_FIND_DATA yapısına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri, veya için sonraki çağrıda kullanılan bir arama tanıtıcıdır `FindNextFile` `FindClose` . İşlev başarısız olursa veya *lpFileName* parametresindeki arama dizesinden dosyaları bulamazsa, dönüş değeri INVALID_HANDLE_VALUE.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı işlevini çağırır `FindFirstFileTransacted` .

## <a name="getfileattributes"></a><a name="getfileattributes"></a> GetFileAttributes

Belirtilen dosya veya dizinin dosya sistemi özniteliklerini işlem temelli bir işlem olarak alır.

```cpp
inline DWORD GetFileAttributes(LPCTSTR lpFileName);
```

### <a name="parameters"></a>Parametreler

*lpFileName*<br/>
Dosya veya dizinin adı.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı işlevini çağırır `GetFileAttributesTransacted` .

## <a name="getfileattributesex"></a><a name="getfileattributesex"></a> GetFileAttributesEx

Belirtilen dosya veya dizinin dosya sistemi özniteliklerini işlem temelli bir işlem olarak alır.

```cpp
inline BOOL GetFileAttributesEx(
    LPCTSTR lpFileName,
    GET_FILEEX_INFO_LEVELS fInfoLevelId,
    LPVOID lpFileInformation);
```

### <a name="parameters"></a>Parametreler

*lpFileName*<br/>
Dosya veya dizinin adı.

*fInfoLevelId*<br/>
Alınacak öznitelik bilgilerinin düzeyi.

*Lpfileınformation*<br/>
Öznitelik bilgilerini alan bir arabelleğin işaretçisi. Bu arabellekte depolanan öznitelik bilgilerinin türü, *fInfoLevelId* değerine göre belirlenir. *FInfoLevelId* parametresi GetFileExInfoStandard ise, bu parametre WIN32_FILE_ATTRIBUTE_DATA yapısına işaret eder.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı işlevini çağırır `GetFileAttributesTransacted` .

## <a name="gethandle"></a><a name="gethandle"></a> GetHandle

İşlem tanıtıcısını döndürür.

```cpp
HANDLE GetHandle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir sınıf için işlem tanıtıcısını döndürür. `CAtlTransactionManager`Bir tanıtıcıya ILIŞTIRILMIŞSE null değerini döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="isfallback"></a><a name="isfallback"></a> Isgeri dönüş

Geri dönüş çağrılarının etkinleştirilip etkinleştirilmeyeceğini belirler.

```cpp
BOOL IsFallback() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sınıfın geri dönüş çağrılarını desteklediği TRUE değerini döndürür. Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="m_bfallback"></a><a name="m_bfallback"></a> m_bFallback

Geri dönüş destekleniyorsa doğru; Aksi takdirde FALSE.

```cpp
BOOL m_bFallback;
```

### <a name="remarks"></a>Açıklamalar

## <a name="m_htransaction"></a><a name="m_htransaction"></a> m_hTransaction

İşlem tanıtıcısı.

```cpp
HANDLE m_hTransaction;
```

### <a name="remarks"></a>Açıklamalar

## <a name="movefile"></a><a name="movefile"></a> MoveFile

Var olan bir dosyayı veya bir dizini, alt öğeleri de dahil olmak üzere işlem temelli bir işlem olarak kaydırır.

```cpp
inline BOOL MoveFile(LPCTSTR lpOldFileName, LPCTSTR lpNewFileName);
```

### <a name="parameters"></a>Parametreler

*lpOldFileName*<br/>
Yerel bilgisayardaki mevcut dosyanın veya dizinin geçerli adı.

*lpNewFileName*<br/>
Dosya veya dizinin yeni adı. Bu ad zaten mevcut olmamalıdır. Yeni bir dosya, farklı bir dosya sisteminde veya sürücüde olabilir. Yeni bir dizin aynı sürücüde olmalıdır.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı işlevini çağırır `MoveFileTransacted` .

## <a name="regcreatekeyex"></a><a name="regcreatekeyex"></a> RegCreateKeyEx

Belirtilen kayıt defteri anahtarını oluşturur ve bir işlem ile ilişkilendirir. Anahtar zaten varsa, işlev onu açar.

```cpp
inline LSTATUS RegCreateKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD dwReserved,
    LPTSTR lpClass,
    DWORD dwOptions,
    REGSAM samDesired,
    CONST LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    PHKEY phkResult,
    LPDWORD lpdwDisposition);
```

### <a name="parameters"></a>Parametreler

*hKey*<br/>
Açık bir kayıt defteri anahtarına yönelik bir tanıtıcı.

*Lpaltanahtar*<br/>
Bu işlevin açtığı veya oluşturduğu alt anahtarın adı.

*Dwayrýlmýþ*<br/>
Bu parametre ayrılmıştır ve sıfır olmalıdır.

*lpClass*<br/>
Bu anahtarın Kullanıcı tanımlı sınıfı. Bu parametre yoksayılabilir. Bu parametre NULL olabilir.

*dwOptions*<br/>
Bu parametre aşağıdaki değerlerden biri olabilir: REG_OPTION_BACKUP_RESTORE, REG_OPTION_NON_VOLATILE veya REG_OPTION_VOLATILE.

*samDesired*<br/>
Anahtar için erişim haklarını belirten bir maske.

*lpSecurityAttributes*<br/>
Döndürülen Tanıtıcının alt süreçler tarafından devralınıp alınmayacağını belirleyen SECURITY_ATTRIBUTES yapısına yönelik işaretçi. *LpSecurityAttributes* null ise, tanıtıcı devralınamaz.

*phkResult*<br/>
Açık veya oluşturulmuş anahtara bir tanıtıcı alan bir değişkene yönelik işaretçi. Anahtar önceden tanımlanmış kayıt defteri anahtarlarından biri değilse, `RegCloseKey` tanıtıcıyı kullanmayı bitirdikten sonra işlevi çağırın.

*lpdwDisposition*<br/>
Şu değerlendirme değerlerinden birini alan bir değişken işaretçisi: REG_CREATED_NEW_KEY veya REG_OPENED_EXISTING_KEY.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri ERROR_SUCCESS. İşlev başarısız olursa, dönüş değeri, Winerror. h içinde tanımlanan sıfır dışı bir hata kodudur.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı işlevini çağırır `RegCreateKeyTransacted` .

## <a name="regdeletekey"></a><a name="regdeletekey"></a> RegDeleteKey

Bir alt anahtarı ve değerlerini, kayıt defterinin belirtilen platforma özgü görünümünden işlem temelli bir işlem olarak siler.

```cpp
inline LSTATUS RegDeleteKeyEx(HKEY hKey, LPCTSTR lpSubKey);
```

### <a name="parameters"></a>Parametreler

*hKey*\
Açık bir kayıt defteri anahtarına yönelik bir tanıtıcı.

*Lpaltanahtar*\
Silinecek anahtarın adı.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri ERROR_SUCCESS. İşlev başarısız olursa, dönüş değeri, Winerror. h içinde tanımlanan sıfır dışı bir hata kodudur.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı işlevini çağırır `RegDeleteKeyTransacted` .

## <a name="regopenkeyex"></a><a name="regopenkeyex"></a> RegOpenKeyEx

Belirtilen kayıt defteri anahtarını açar ve bir işlem ile ilişkilendirir.

```cpp
inline LSTATUS RegOpenKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD ulOptions,
    REGSAM samDesired,
    PHKEY phkResult);
```

### <a name="parameters"></a>Parametreler

*hKey*<br/>
Açık bir kayıt defteri anahtarına yönelik bir tanıtıcı.

*Lpaltanahtar*<br/>
Açılacak kayıt defteri alt anahtarının adı.

*ulOptions*<br/>
Bu parametre ayrılmıştır ve sıfır olmalıdır.

*samDesired*<br/>
Anahtar için erişim haklarını belirten bir maske.

*phkResult*<br/>
Açık veya oluşturulmuş anahtara bir tanıtıcı alan bir değişkene yönelik işaretçi. Anahtar önceden tanımlanmış kayıt defteri anahtarlarından biri değilse, `RegCloseKey` tanıtıcıyı kullanmayı bitirdikten sonra işlevi çağırın.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri ERROR_SUCCESS. İşlev başarısız olursa, dönüş değeri, Winerror. h içinde tanımlanan sıfır dışı bir hata kodudur

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı işlevini çağırır `RegOpenKeyTransacted` .

## <a name="rollback"></a><a name="rollback"></a> Etkin

İşlemin geri alınmasına yönelik istekler.

```cpp
inline BOOL Rollback();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı işlevini çağırır `RollbackTransaction` .

## <a name="setfileattributes"></a><a name="setfileattributes"></a> SetFileAttributes

Bir dosya veya dizinin özniteliklerini işlem temelli bir işlem olarak ayarlar.

```cpp
inline BOOL SetFileAttributes(LPCTSTR lpFileName, DWORD dwAttributes);
```

### <a name="parameters"></a>Parametreler

*lpFileName*<br/>
Dosya veya dizinin adı.

*dwAttributes*<br/>
Dosya için ayarlanacak dosya öznitelikleri. Daha fazla bilgi için bkz. [Setfileattributestransasiyonu](/windows/win32/api/winbase/nf-winbase-setfileattributestransactedw).

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı işlevini çağırır `SetFileAttributesTransacted` .

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM Masaüstü Bileşenleri](../../atl/atl-com-desktop-components.md)
