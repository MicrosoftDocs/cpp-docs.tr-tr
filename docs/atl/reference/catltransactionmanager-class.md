---
title: CAtlTransactionManager Sınıfı
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
ms.openlocfilehash: 5c2814f963ea4814e0d7585e0e4d6dda26c1f04d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321318"
---
# <a name="catltransactionmanager-class"></a>CAtlTransactionManager Sınıfı

CAtlTransactionManager sınıfı, Kernel Transaction Manager (KTM) işlevlerine bir sarmalayıcı sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CAtlTransactionManager;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[~CAtlTransactionManager](#dtor)|CAtlTransactionManager yıkıcı.|
|[Catltransactionmanager](#catltransactionmanager)|CAtlTransactionManager oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Kapat](#close)|Hareket tutamacından birini kapatır.|
|[İşleme](#commit)|Hareketin işlenmesini talep eder.|
|[Oluştur](#create)|Hareket tutamacını oluşturur.|
|[Createfile](#createfile)|İşlenen bir işlem olarak bir dosya, dosya akışı veya dizin oluşturur veya açar.|
|[Dosyayı Sil](#deletefile)|İşlenen bir işlem olarak varolan bir dosyayı siler.|
|[Findfirstfile](#findfirstfile)|İşlenen bir işlem olarak bir dosya veya alt dizini arar.|
|[Dosya Özelliklerini Al](#getfileattributes)|İşlenen bir işlem olarak belirli bir dosya veya dizin için dosya sistem özniteliklerini alır.|
|[GetFileAttributesEx](#getfileattributesex)|İşlenen bir işlem olarak belirli bir dosya veya dizin için dosya sistem özniteliklerini alır.|
|[GetHandle](#gethandle)|Hareket tutamacını döndürür.|
|[IsFallback](#isfallback)|Geri dönüş çağrılarının etkin olup olmadığını belirler.|
|[Movefile](#movefile)|Varolan bir dosyayı veya çocukları da dahil olmak üzere bir dizini işleyen bir işlem olarak taşır.|
|[RegCreateKeyEx](#regcreatekeyex)|Belirtilen kayıt defteri anahtarını oluşturur ve bir hareketle ilişkilendirer. Anahtar zaten varsa, işlev açar.|
|[RegDeleteKey](#regdeletekey)|Bir alt anahtarı ve değerlerini, kayıt defterinin işlenme işlemi olarak belirtilen platforma özgü görünümünden siler.|
|[RegOpenKeyEx](#regopenkeyex)|Belirtilen kayıt defteri anahtarını açar ve bir hareketle ilişkilendirin.|
|[Geri alma](#rollback)|Hareketin geri alınmasını talep etmek.|
|[SetFileAttributes](#setfileattributes)|İşlenen bir işlem olarak bir dosya veya dizin özniteliklerini ayarlar.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[m_bFallback](#m_bfallback)|Geri dönüş desteklenirse DOĞRU; YANLIŞ aksi takdirde.|
|[m_hTransaction](#m_htransaction)|Hareket tutamacı.|

## <a name="remarks"></a>Açıklamalar

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[ATL::CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltransactionmanager.h

## <a name="catltransactionmanager"></a><a name="dtor"></a>~CAtlTransactionManager

CAtlTransactionManager yıkıcı.

```
virtual ~CAtlTransactionManager();
```

### <a name="remarks"></a>Açıklamalar

Normal işlemede, hareket otomatik olarak kaydedilir ve kapatılır. Yıkıcı bir özel durum gevşemesi sırasında çağrılırsa, hareket geri alınır ve kapatılır.

## <a name="catltransactionmanager"></a><a name="catltransactionmanager"></a>Catltransactionmanager

CAtlTransactionManager oluşturucu.

```
CAtlTransactionManager(BOOL bFallback = TRUE, BOOL bAutoCreateTransaction = TRUE);
```

### <a name="parameters"></a>Parametreler

*bFallback*<br/>
TRUE destek geri dönüşünü gösterir. İşlenen işlev başarısız olursa, sınıf otomatik olarak "işlemeyen" işlevi çağırır. FALSE hiçbir "geri dönüş" çağrıları gösterir.

*bAutoCreateİşlem*<br/>
TRUE, işlem işleyicisinin oluşturucuda otomatik olarak oluşturulduğunu gösterir. YANLIŞ olmadığını gösterir.

### <a name="remarks"></a>Açıklamalar

## <a name="close"></a><a name="close"></a>Yakın

Hareket tutamacını kapatır.

```
inline BOOL Close();
```

### <a name="return-value"></a>Dönüş Değeri

Doğru eğer başarılı; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu sarıcı `CloseHandle` işlevi çağırır. Yöntem otomatik olarak yıkıcı olarak adlandırılır.

## <a name="commit"></a><a name="commit"></a>Tamamlama

Hareketin işlenmesini talep eder.

```
inline BOOL Commit();
```

### <a name="return-value"></a>Dönüş Değeri

Doğru eğer başarılı; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu sarıcı `CommitTransaction` işlevi çağırır. Yöntem otomatik olarak yıkıcı olarak adlandırılır.

## <a name="create"></a><a name="create"></a>Oluşturmak

Hareket tutamacını oluşturur.

```
inline BOOL Create();
```

### <a name="return-value"></a>Dönüş Değeri

Doğru eğer başarılı; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu sarıcı `CreateTransaction` işlevi çağırır. Kontrol edin

## <a name="createfile"></a><a name="createfile"></a>Createfile

İşlenen bir işlem olarak bir dosya, dosya akışı veya dizin oluşturur veya açar.

```
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
Oluşturulacak veya açılacak bir nesnenin adı.

*dwDesiredAccess*<br/>
Her ikisi de veya ikisi birden (sıfır) olarak özetlenebilir nesneye erişim. En sık kullanılan değerler GENERIC_READ, GENERIC_WRITE veya her ikisi dir: GENERIC_READ &#124; GENERIC_WRITE.

*dwShareMode*<br/>
Bir nesnenin paylaşım modu, okunabilir, yazar, her ikisi de, silinebilir, bunların tümü veya hiçbiri: 0, FILE_SHARE_DELETE, FILE_SHARE_READ, FILE_SHARE_WRITE.

*lpSecurityAttributes*<br/>
İsteğe bağlı güvenlik tanımlayıcısı içeren ve döndürülen tanıtıcının alt işlemler tarafından devralınıp alınamayacağını da belirleyen SECURITY_ATTRIBUTES bir yapıya işaretçi. Parametre NULL olabilir.

*dwCreationDisposition*<br/>
Var olan ve olmayan dosyalar üzerinde yapılacak bir eylem. Bu parametre birleştirilemeyen aşağıdaki değerlerden biri olmalıdır: CREATE_ALWAYS, CREATE_NEW, OPEN_ALWAYS, OPEN_EXISTING veya TRUNCATE_EXISTING.

*dwFlagsAndAttributes*<br/>
Dosya öznitelikleri ve bayraklar. Bu parametre, kullanılabilir dosya özniteliklerinin herhangi bir birleşimini içerebilir (FILE_ATTRIBUTE_*). Diğer tüm dosya öznitelikleri FILE_ATTRIBUTE_NORMAL geçersiz kılar. Bu parametre, arabelleğe alma\*davranışı, erişim modları ve diğer özel amaçlı bayrakları denetlemek için bayrak (FILE_FLAG_) birleşimleri de içerebilir. Bunlar FILE_ATTRIBUTE_\* değerleri yle birleştirir.

*hTemplateFile*<br/>
GENERIC_READ erişim hakkı olan bir şablon dosyasına geçerli bir tanıtıcı. Şablon dosyası, oluşturulan dosya için dosya öznitelikleri ve genişletilmiş öznitelikleri sağlar. Bu parametre NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Nesneye erişmek için kullanılabilecek bir tanıtıcı döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sarıcı `CreateFileTransacted` işlevi çağırır.

## <a name="deletefile"></a><a name="deletefile"></a>Dosyayı Sil

İşlenen bir işlem olarak varolan bir dosyayı siler.

```
inline BOOL DeleteFile(LPCTSTR lpFileName);
```

### <a name="parameters"></a>Parametreler

*lpFileName*<br/>
Silinecek dosyanın adı.

### <a name="remarks"></a>Açıklamalar

Bu sarıcı `DeleteFileTransacted` işlevi çağırır.

## <a name="findfirstfile"></a><a name="findfirstfile"></a>Findfirstfile

İşlenen bir işlem olarak bir dosya veya alt dizini arar.

```
inline HANDLE FindFirstFile(
    LPCTSTR lpFileName,
    WIN32_FIND_DATA* pNextInfo);
```

### <a name="parameters"></a>Parametreler

*lpFileName*<br/>
Dizin veya yol ve aranacak dosya adı. Bu parametre, yıldız işareti (*) veya soru işareti () gibi joker karakter içerebilir.

*pNextInfo*<br/>
Bulunan bir dosya veya alt dizin hakkında bilgi alan WIN32_FIND_DATA yapıya işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, iade değeri sonraki bir çağrıda kullanılan `FindNextFile` `FindClose`bir arama tanıtıcısı veya . İşlev *lpFileName* parametresinde arama dizesinden dosyaları bulamazsa veya bulamazsa, iade değeri INVALID_HANDLE_VALUE.

### <a name="remarks"></a>Açıklamalar

Bu sarıcı `FindFirstFileTransacted` işlevi çağırır.

## <a name="getfileattributes"></a><a name="getfileattributes"></a>Dosya Özelliklerini Al

İşlenen bir işlem olarak belirli bir dosya veya dizin için dosya sistem özniteliklerini alır.

```
inline DWORD GetFileAttributes(LPCTSTR lpFileName);
```

### <a name="parameters"></a>Parametreler

*lpFileName*<br/>
Dosyanın veya dizinin adı.

### <a name="remarks"></a>Açıklamalar

Bu sarıcı `GetFileAttributesTransacted` işlevi çağırır.

## <a name="getfileattributesex"></a><a name="getfileattributesex"></a>GetFileAttributesEx

İşlenen bir işlem olarak belirli bir dosya veya dizin için dosya sistem özniteliklerini alır.

```
inline BOOL GetFileAttributesEx(
    LPCTSTR lpFileName,
    GET_FILEEX_INFO_LEVELS fInfoLevelId,
    LPVOID lpFileInformation);
```

### <a name="parameters"></a>Parametreler

*lpFileName*<br/>
Dosyanın veya dizinin adı.

*fInfoLevelId*<br/>
Alınacak öznitelik bilgisi düzeyi.

*lpFileInformation*<br/>
Öznitelik bilgilerini alan arabellek için bir işaretçi. Bu arabellekte depolanan öznitelik bilgilerinin türü *fInfoLevelId*değerine göre belirlenir. *fInfoLevelId* parametresi GetFileExInfoStandard ise bu parametre WIN32_FILE_ATTRIBUTE_DATA bir yapıya işaret ediyor.

### <a name="remarks"></a>Açıklamalar

Bu sarıcı `GetFileAttributesTransacted` işlevi çağırır.

## <a name="gethandle"></a><a name="gethandle"></a>GetHandle

Hareket tutamacını döndürür.

```
HANDLE GetHandle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir sınıfın hareket tutamacını döndürür. Bir tutamak bağlı değilse NULL `CAtlTransactionManager` döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="isfallback"></a><a name="isfallback"></a>IsFallback

Geri dönüş çağrılarının etkin olup olmadığını belirler.

```
BOOL IsFallback() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE döndürür sınıf geri dönüş çağrıları destekler. YANLIŞ aksi takdirde.

### <a name="remarks"></a>Açıklamalar

## <a name="m_bfallback"></a><a name="m_bfallback"></a>m_bFallback

Geri dönüş desteklenirse DOĞRU; YANLIŞ aksi takdirde.

```
BOOL m_bFallback;
```

### <a name="remarks"></a>Açıklamalar

## <a name="m_htransaction"></a><a name="m_htransaction"></a>m_hTransaction

Hareket tutamacı.

```
HANDLE m_hTransaction;
```

### <a name="remarks"></a>Açıklamalar

## <a name="movefile"></a><a name="movefile"></a>Movefile

Varolan bir dosyayı veya çocukları da dahil olmak üzere bir dizini işleyen bir işlem olarak taşır.

```
inline BOOL MoveFile(LPCTSTR lpOldFileName, LPCTSTR lpNewFileName);
```

### <a name="parameters"></a>Parametreler

*lpOldFileName*<br/>
Yerel bilgisayardaki varolan dosyanın veya dizinin geçerli adı.

*lpNewFileName*<br/>
Dosya veya dizin için yeni ad. Bu ad zaten var olmamalıdır. Yeni bir dosya farklı bir dosya sistemi veya sürücü üzerinde olabilir. Yeni bir dizin aynı sürücüde olmalıdır.

### <a name="remarks"></a>Açıklamalar

Bu sarıcı `MoveFileTransacted` işlevi çağırır.

## <a name="regcreatekeyex"></a><a name="regcreatekeyex"></a>RegCreateKeyEx

Belirtilen kayıt defteri anahtarını oluşturur ve bir hareketle ilişkilendirer. Anahtar zaten varsa, işlev açar.

```
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

*Hkey*<br/>
Açık bir kayıt defteri anahtarının tutamacı.

*lpSubKey*<br/>
Bu işlevin açtığı veya oluşturduğu bir alt anahtarın adı.

*dwAyrılmış*<br/>
Bu parametre ayrılmıştır ve sıfır olmalıdır.

*lpClass*<br/>
Bu anahtarın kullanıcı tanımlı sınıfı. Bu parametre yoksayılabilir. Bu parametre NULL olabilir.

*Dwoptions*<br/>
Bu parametre aşağıdaki değerlerden biri olabilir: REG_OPTION_BACKUP_RESTORE, REG_OPTION_NON_VOLATILE veya REG_OPTION_VOLATILE.

*samDesired*<br/>
Anahtarın erişim haklarını belirten bir maske.

*lpSecurityAttributes*<br/>
Döndürülen tanıtıcının alt işlemler tarafından devralınıp alınamayacağını belirleyen SECURITY_ATTRIBUTES bir yapıyı işaretle. *lpSecurityAttributes* NULL ise, işletmek devralınamaz.

*phkResult*<br/>
Açılan veya oluşturulan anahtara tutamacı alan bir değişkenin işaretçisi. Anahtar önceden tanımlanmış kayıt defteri anahtarlarından biri değilse, tutamacı nı kullanmayı bitirdikten sonra `RegCloseKey` işlevi arayın.

*lpdwDisposition*<br/>
Aşağıdaki eğilim değerlerinden birini alan bir değişkene işaretçi: REG_CREATED_NEW_KEY veya REG_OPENED_EXISTING_KEY.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, iade değeri ERROR_SUCCESS. İşlev başarısız olursa, iade değeri Winerror.h'de tanımlanan sıfır olmayan bir hata kodudur.

### <a name="remarks"></a>Açıklamalar

Bu sarıcı `RegCreateKeyTransacted` işlevi çağırır.

## <a name="regdeletekey"></a><a name="regdeletekey"></a>RegDeleteKey

Bir alt anahtarı ve değerlerini, kayıt defterinin işlenme işlemi olarak belirtilen platforma özgü görünümünden siler.

```
inline LSTATUS RegDeleteKeyEx(HKEY hKey, LPCTSTR lpSubKey);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Hkey*|Açık bir kayıt defteri anahtarının tutamacı.|
|*lpSubKey*|Silinecek anahtarın adı.|

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, iade değeri ERROR_SUCCESS. İşlev başarısız olursa, iade değeri Winerror.h'de tanımlanan sıfır olmayan bir hata kodudur.

### <a name="remarks"></a>Açıklamalar

Bu sarıcı `RegDeleteKeyTransacted` işlevi çağırır.

## <a name="regopenkeyex"></a><a name="regopenkeyex"></a>RegOpenKeyEx

Belirtilen kayıt defteri anahtarını açar ve bir hareketle ilişkilendirin.

```
inline LSTATUS RegOpenKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD ulOptions,
    REGSAM samDesired,
    PHKEY phkResult);
```

### <a name="parameters"></a>Parametreler

*Hkey*<br/>
Açık bir kayıt defteri anahtarının tutamacı.

*lpSubKey*<br/>
Açılacak kayıt defteri alt anahtarının adı.

*ulOptions*<br/>
Bu parametre ayrılmıştır ve sıfır olmalıdır.

*samDesired*<br/>
Anahtarın erişim haklarını belirten bir maske.

*phkResult*<br/>
Açılan veya oluşturulan anahtara tutamacı alan bir değişkenin işaretçisi. Anahtar önceden tanımlanmış kayıt defteri anahtarlarından biri değilse, tutamacı nı kullanmayı bitirdikten sonra `RegCloseKey` işlevi arayın.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, iade değeri ERROR_SUCCESS. İşlev başarısız olursa, iade değeri Winerror.h'de tanımlanan sıfır olmayan bir hata kodudur

### <a name="remarks"></a>Açıklamalar

Bu sarıcı `RegOpenKeyTransacted` işlevi çağırır.

## <a name="rollback"></a><a name="rollback"></a>Geri alma

Hareketin geri alınmasını talep etmek.

```
inline BOOL Rollback();
```

### <a name="return-value"></a>Dönüş Değeri

Doğru eğer başarılı; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu sarıcı `RollbackTransaction` işlevi çağırır.

## <a name="setfileattributes"></a><a name="setfileattributes"></a>SetFileAttributes

İşlenen bir işlem olarak bir dosya veya dizin özniteliklerini ayarlar.

```
inline BOOL SetFileAttributes(LPCTSTR lpFileName, DWORD dwAttributes);
```

### <a name="parameters"></a>Parametreler

*lpFileName*<br/>
Dosyanın veya dizinin adı.

*dwÖzler*<br/>
Dosya, dosya için ayarlanan öznitelikleri. Daha fazla bilgi için bkz: [SetFileAttributesTransacted](/windows/win32/api/winbase/nf-winbase-setfileattributestransactedw).

### <a name="remarks"></a>Açıklamalar

Bu sarıcı `SetFileAttributesTransacted` işlevi çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM Masaüstü Bileşenleri](../../atl/atl-com-desktop-components.md)
