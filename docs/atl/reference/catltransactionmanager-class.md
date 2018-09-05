---
title: CAtlTransactionManager sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAtlTransactionManager class
ms.assetid: b01732dc-1d16-4b42-bfac-b137fca2b740
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1217fe9c7bbb43b578a7f7236c69531f04464a44
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755927"
---
# <a name="catltransactionmanager-class"></a>CAtlTransactionManager sınıfı

CAtlTransactionManager sınıfı Çekirdek İşlem Yöneticisi (KTM) işlevleri için bir sarmalayıcı sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CAtlTransactionManager;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[~ CAtlTransactionManager](#dtor)|CAtlTransactionManager yıkıcı.|
|[CAtlTransactionManager](#catltransactionmanager)|CAtlTransactionManager Oluşturucusu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Kapat](#close)|Bir işlem tanıtıcısı kapatır.|
|[İşleme](#commit)|İstekleri işlemin yürütülmesi.|
|[Oluşturma](#create)|Hareket işleyici oluşturur.|
|[CreateFile](#createfile)|Oluşturur veya bir dosya, dosya akışı veya işlem temelli bir işlem olarak dizini açar.|
|[DeleteFile](#deletefile)|Bir hizmetteki bir işlem olarak mevcut bir dosyayı siler.|
|[FindFirstFile](#findfirstfile)|Bir hizmetteki bir işlem olarak bir dosya veya alt dizin arar.|
|[GetFileAttributes](#getfileattributes)|Bir hizmetteki bir işlem olarak belirtilen dosya veya dizin dosya sistemi özniteliklerini alır.|
|[GetFileAttributesEx](#getfileattributesex)|Bir hizmetteki bir işlem olarak belirtilen dosya veya dizin dosya sistemi özniteliklerini alır.|
|[GetHandle](#gethandle)|Hareket işleyicisini döndürür.|
|[IsFallback](#isfallback)|Geri dönüş çağrıları etkin olup olmadığını belirler.|
|[MoveFile](#movefile)|Var olan bir dosya veya dizin hizmetteki bir işlem olarak alt öğeleri dahil olmak üzere taşır.|
|[RegCreateKeyEx](#regcreatekeyex)|Belirtilen kayıt defteri anahtarı oluşturur ve bir işlem ile ilişkilendirir. İşlev anahtarı zaten varsa, açar.|
|[RegDeleteKey](#regdeletekey)|Bir alt anahtarı ve değerleri kayıt defterinde belirtilen platforma özgü görünümünden bir hizmetteki bir işlem olarak siler.|
|[RegOpenKeyEx](#regopenkeyex)|Belirtilen kayıt defteri anahtarı açılır ve bir işlem ile ilişkilendirir.|
|[Geri alma](#rollback)|İşlem geri alınamaz istekler.|
|[SetFileAttributes](#setfileattributes)|Bir dosya veya dizin özniteliklerini, hizmetteki bir işlem olarak ayarlar.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[m_bFallback](#m_bfallback)|Geri dönüş destekleniyorsa TRUE; FALSE Aksi takdirde.|
|[m_hTransaction](#m_htransaction)|Hareket işleyici.|

## <a name="remarks"></a>Açıklamalar

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[ATL::CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** atltransactionmanager.h

##  <a name="dtor"></a>  ~ CAtlTransactionManager

CAtlTransactionManager yıkıcı.

```
virtual ~CAtlTransactionManager();
```

### <a name="remarks"></a>Açıklamalar

Normal işlem, işlem otomatik olarak kabul edilen ve kapatılır. Sırasında bir özel durumu geriye doğru izleme yok Edicisi çağrılır, işlem geri alındı ve kapatıldı.

##  <a name="catltransactionmanager"></a>  CAtlTransactionManager

CAtlTransactionManager Oluşturucusu.

```
CAtlTransactionManager(BOOL bFallback = TRUE, BOOL bAutoCreateTransaction = TRUE);
```

### <a name="parameters"></a>Parametreler

*bFallback*  
TRUE, destek geri dönüş gösterir. İşlenen işlev başarısız olursa sınıfı otomatik olarak "işlem temelli olmayan" işlevi çağırır. FALSE, "temel" çağrı gösterir.

*bAutoCreateTransaction*  
TRUE, hareket işleyicisi oluşturucuda otomatik olarak oluşturulduğunu gösterir. FALSE etkinleştirilmediğini gösterir.

### <a name="remarks"></a>Açıklamalar

##  <a name="close"></a>  Kapat

İşlem tanıtıcısı kapatır.

```
inline BOOL Close();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı çağırır `CloseHandle` işlevi. Yöntem, yıkıcı otomatik olarak çağrılır.

##  <a name="commit"></a>  İşleme

İstekleri işlemin yürütülmesi.

```
inline BOOL Commit();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı çağırır `CommitTransaction` işlevi. Yöntem, yıkıcı otomatik olarak çağrılır.

##  <a name="create"></a>  Oluşturma

Hareket işleyici oluşturur.

```
inline BOOL Create();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı çağırır `CreateTransaction` işlevi. Bunun için işaretleyin

##  <a name="createfile"></a>  CreateFile

Oluşturur veya bir dosya, dosya akışı veya işlem temelli bir işlem olarak dizini açar.

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

*lpDosyaAdı*  
Oluşturulacak veya açılmış bir nesnenin adı.

*dwDesiredAccess*  
Okuma, yazma, her iki ya da hiçbiri (sıfır) özetlenebilir nesneye erişim. GENERIC_READ, GENERIC_WRITE veya her ikisi de en sık kullanılan değerler şunlardır: GENERIC_READ &#124; GENERIC_WRITE.

*dwShareMode*  
Paylaşım modu okuma, yazma, her ikisi de olması, silme, bunların tümü veya hiçbiri bir nesnenin: 0, FILE_SHARE_DELETE, FILE_SHARE_READ FILE_SHARE_WRITE.

*lpSecurityAttributes*  
Bir işaretçi SECURITY_ATTRIBUTES yapısına bir isteğe bağlı bir güvenlik tanımlayıcısı içerir ve ayrıca döndürülen tanıtıcının alt işlemler tarafından devralınıp olup olmadığını belirler. Parametre NULL olabilir.

*dwCreationDisposition*  
Mevcut ve mevcut dosyaları üzerinde gerçekleştirilecek bir eylem. Bu parametre birleştirilemez aşağıdaki değerlerden biri olmalıdır: CREATE_ALWAYS, CREATE_NEW, OPEN_ALWAYS, OPEN_EXISTING veya TRUNCATE_EXISTING.

*dwFlagsAndAttributes*  
Dosya öznitelikleri ve bayrakları. Bu parametre, kullanılabilir bir dosya öznitelikleri (FILE_ATTRIBUTE_ *) herhangi bir birleşimini içerebilir. Diğer tüm dosya özniteliklerini FILE_ATTRIBUTE_NORMAL geçersiz kılar. Bu parametre bayrakları birleşimlerini de içerebilir (FILE_FLAG_\*) davranışı ara belleğe almanın daha fazla denetim için erişim modları ve diğer özel amaçlı bayraklar. Bunları herhangi FILE_ATTRIBUTE_ ile birleştirerek\* değerleri.

*hTemplateFile*  
Doğru GENERIC_READ erişimi olan bir şablon dosyası için geçerli bir tanıtıcı. Şablon dosyası, dosya öznitelikleri ve oluşturulan dosyanın genişletilmiş öznitelikleri sağlar. Bu parametre NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Nesneye erişmek için kullanılan bir tanıtıcı döndürür.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı çağırır `CreateFileTransacted` işlevi.

##  <a name="deletefile"></a>  DeleteFile

Bir hizmetteki bir işlem olarak mevcut bir dosyayı siler.

```
inline BOOL DeleteFile(LPCTSTR lpFileName);
```

### <a name="parameters"></a>Parametreler

*lpDosyaAdı*  
Silinecek dosyanın adı.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı çağırır `DeleteFileTransacted` işlevi.

##  <a name="findfirstfile"></a>  FindFirstFile

Bir hizmetteki bir işlem olarak bir dosya veya alt dizin arar.

```
inline HANDLE FindFirstFile(
    LPCTSTR lpFileName,
    WIN32_FIND_DATA* pNextInfo);
```

### <a name="parameters"></a>Parametreler

*lpDosyaAdı*  
Dizin veya yol ve dosya adı, aranacak. Bu parametre, yıldız işareti (*) veya bir soru işareti () gibi joker karakterler içerebilir.

*pNextInfo*  
Bulunan dosya veya alt bilgi alan WIN32_FIND_DATA yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, dönüş değeri bir yapılan sonraki çağrıda kullanılan bir arama işleyicisidir `FindNextFile` veya `FindClose`. İşlev başarısız olursa veya arama dizesinde dosyalarından bulamazsa *lpDosyaAdı* parametresi, dönüş değeri, INVALID_HANDLE_VALUE.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı çağırır `FindFirstFileTransacted` işlevi.

##  <a name="getfileattributes"></a>  GetFileAttributes

Bir hizmetteki bir işlem olarak belirtilen dosya veya dizin dosya sistemi özniteliklerini alır.

```
inline DWORD GetFileAttributes(LPCTSTR lpFileName);
```

### <a name="parameters"></a>Parametreler

*lpDosyaAdı*  
Dosya veya dizin adı.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı çağırır `GetFileAttributesTransacted` işlevi.

##  <a name="getfileattributesex"></a>  GetFileAttributesEx

Bir hizmetteki bir işlem olarak belirtilen dosya veya dizin dosya sistemi özniteliklerini alır.

```
inline BOOL GetFileAttributesEx(
    LPCTSTR lpFileName,
    GET_FILEEX_INFO_LEVELS fInfoLevelId,
    LPVOID lpFileInformation);
```

### <a name="parameters"></a>Parametreler

*lpDosyaAdı*  
Dosya veya dizin adı.

*fInfoLevelId*  
Öznitelik bilgileri almak için düzeyi.

*lpFileInformation*  
Öznitelik bilgileri alan arabellek için işaretçi. Bu arabelleğine depolanan öznitelik bilgileri türü değeri tarafından belirlenir *fInfoLevelId*. Varsa *fInfoLevelId* parametredir GetFileExInfoStandard sonra bu parametreyi WIN32_FILE_ATTRIBUTE_DATA yapısına işaret eder.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı çağırır `GetFileAttributesTransacted` işlevi.

##  <a name="gethandle"></a>  GetHandle

Hareket işleyicisini döndürür.

```
HANDLE GetHandle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir sınıf için hareket işleyicisini döndürür. NULL döndürür `CAtlTransactionManager` işleyici bağlı değil.

### <a name="remarks"></a>Açıklamalar

##  <a name="isfallback"></a>  IsFallback

Geri dönüş çağrıları etkin olup olmadığını belirler.

```
BOOL IsFallback() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sınıfı destekler geri dönüş çağrıları olan TRUE döndürür. FALSE Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

##  <a name="m_bfallback"></a>  m_bFallback

Geri dönüş destekleniyorsa TRUE; FALSE Aksi takdirde.

```
BOOL m_bFallback;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="m_htransaction"></a>  m_hTransaction

Hareket işleyici.

```
HANDLE m_hTransaction;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="movefile"></a>  MoveFile

Var olan bir dosya veya dizin hizmetteki bir işlem olarak alt öğeleri dahil olmak üzere taşır.

```
inline BOOL MoveFile(LPCTSTR lpOldFileName, LPCTSTR lpNewFileName);
```

### <a name="parameters"></a>Parametreler

*lpOldFileName*  
Var olan dosya veya dizin yerel bilgisayardaki geçerli adı.

*lpNewFileName*  
Dosya veya dizin için yeni ad. Bu ad zaten mevcut olmamalıdır. Yeni bir dosya, farklı bir dosya sistemi veya sürücü üzerinde olabilir. Yeni bir dizin aynı sürücüde olmalıdır.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı çağırır `MoveFileTransacted` işlevi.

##  <a name="regcreatekeyex"></a>  RegCreateKeyEx

Belirtilen kayıt defteri anahtarı oluşturur ve bir işlem ile ilişkilendirir. İşlev anahtarı zaten varsa, açar.

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

*hKey*  
Bir kayıt defteri anahtarı için bir tanıtıcı.

*lpSubKey*  
Bu işlev açar veya oluşturur bir alt anahtar adı.

*dwReserved*  
Bu parametre ayrılmıştır ve sıfır olmalıdır.

*lpClass*  
Bu anahtarın kullanıcı tanımlı sınıf. Bu parametreyi yok sayılabilir. Bu parametre NULL olabilir.

*dwOptions*  
Bu parametre aşağıdaki değerlerden biri olabilir: REG_OPTION_BACKUP_RESTORE, REG_OPTION_NON_VOLATILE veya REG_OPTION_VOLATILE.

*samDesired*  
Anahtar için erişim haklarını belirtir maskesi.

*lpSecurityAttributes*  
Döndürülen tanıtıcının alt işlemler tarafından devralınıp alınmayacağını belirleyen SECURITY_ATTRIBUTES yapı işaretçisi. Varsa *lpSecurityAttributes* null, tanıtıcı devralınamaz.

*phkResult*  
Açılan veya oluşturulan anahtarı için bir tanıtıcı alan bir değişken için bir işaretçi. Anahtar önceden tanımlanmış bir kayıt defteri anahtarlarından biri değilse, çağrı `RegCloseKey` işleci kullanılarak tamamladıktan sonra çalışmaz.

*lpdwDisposition*  
Aşağıdaki değerlendirme değerlerinden birini alan bir değişken işaretçisi: REG_CREATED_NEW_KEY veya REG_OPENED_EXISTING_KEY.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, döndürülen değer ERROR_SUCCESS olur. İşlev başarısız olursa, döndürülen değer wınerror içinde tanımlanan bir sıfır olmayan hata kodudur.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı çağırır `RegCreateKeyTransacted` işlevi.

##  <a name="regdeletekey"></a>  RegDeleteKey

Bir alt anahtarı ve değerleri kayıt defterinde belirtilen platforma özgü görünümünden bir hizmetteki bir işlem olarak siler.

```
inline LSTATUS RegDeleteKeyEx(HKEY hKey, LPCTSTR lpSubKey);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*hKey*|Bir kayıt defteri anahtarı için bir tanıtıcı.|
|*lpSubKey*|Silinecek anahtar adı.|

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, döndürülen değer ERROR_SUCCESS olur. İşlev başarısız olursa, döndürülen değer wınerror içinde tanımlanan bir sıfır olmayan hata kodudur.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı çağırır `RegDeleteKeyTransacted` işlevi.

##  <a name="regopenkeyex"></a>  RegOpenKeyEx

Belirtilen kayıt defteri anahtarı açılır ve bir işlem ile ilişkilendirir.

```
inline LSTATUS RegOpenKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD ulOptions,
    REGSAM samDesired,
    PHKEY phkResult);
```

### <a name="parameters"></a>Parametreler

*hKey*  
Bir kayıt defteri anahtarı için bir tanıtıcı.

*lpSubKey*  
Açılması için kayıt defteri alt anahtarı adı.

*ulOptions*  
Bu parametre ayrılmıştır ve sıfır olmalıdır.

*samDesired*  
Anahtar için erişim haklarını belirtir maskesi.

*phkResult*  
Açılan veya oluşturulan anahtarı için bir tanıtıcı alan bir değişken için bir işaretçi. Anahtar önceden tanımlanmış bir kayıt defteri anahtarlarından biri değilse, çağrı `RegCloseKey` işleci kullanılarak tamamladıktan sonra çalışmaz.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, döndürülen değer ERROR_SUCCESS olur. İşlev başarısız olursa, döndürülen değer wınerror içinde tanımlanan bir sıfır dışında hata kodu.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı çağırır `RegOpenKeyTransacted` işlevi.

##  <a name="rollback"></a>  Geri alma

İşlem geri alınamaz istekler.

```
inline BOOL Rollback();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı çağırır `RollbackTransaction` işlevi.

##  <a name="setfileattributes"></a>  SetFileAttributes

Bir dosya veya dizin özniteliklerini, hizmetteki bir işlem olarak ayarlar.

```
inline BOOL SetFileAttributes(LPCTSTR lpFileName, DWORD dwAttributes);
```

### <a name="parameters"></a>Parametreler

*lpDosyaAdı*  
Dosya veya dizin adı.

*dwAttributes*  
Dosya için ayarlanacak dosya öznitelikleri. Daha fazla bilgi için [SetFileAttributesTransacted](/windows/desktop/api/winbase/nf-winbase-setfileattributestransacteda).

### <a name="remarks"></a>Açıklamalar

Bu sarmalayıcı çağırır `SetFileAttributesTransacted` işlevi.

## <a name="see-also"></a>Ayrıca Bkz.

[ATL COM Masaüstü Bileşenleri](../../atl/atl-com-desktop-components.md)
