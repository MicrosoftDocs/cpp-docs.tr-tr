---
title: CAtlTransactionManager sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
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
caps.latest.revision: 25
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0def8aa809cd1ccc115ccc2a09b1ae752316098f
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="catltransactionmanager-class"></a>CAtlTransactionManager sınıfı
CAtlTransactionManager sınıfı Çekirdek İşlem Yöneticisi (KTM) işlevleri için sarmalayıcı sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
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
|[Tamamlama](#commit)|İşlem tamamlanan istek sayısı.|  
|[Oluşturma](#create)|İşlem tanıtıcısı oluşturur.|  
|[CreateFile](#createfile)|Oluşturur veya bir dosya, dosya akışı ya da dizin hizmetteki bir işlem olarak açar.|  
|[DeleteFile](#deletefile)|Varolan bir dosyanın hizmetteki bir işlem olarak siler.|  
|[FindFirstFile](#findfirstfile)|Bir dosya veya alt dizin için bir dizin hizmetteki bir işlem olarak arar.|  
|[GetFileAttributes](#getfileattributes)|Belirtilen dosya veya dizin dosya sistemi özniteliklerini hizmetteki bir işlem olarak alır.|  
|[GetFileAttributesEx](#getfileattributesex)|Belirtilen dosya veya dizin dosya sistemi özniteliklerini hizmetteki bir işlem olarak alır.|  
|[GetHandle](#gethandle)|İşlem tanıtıcısı döndürür.|  
|[IsFallback](#isfallback)|Geri dönüş çağrılarının etkinleştirilip etkinleştirilmediğini belirler.|  
|[MoveFile](#movefile)|Varolan bir dosya veya alt öğelerini hizmetteki bir işlem olarak dahil olmak üzere bir dizin taşır.|  
|[RegCreateKeyEx](#regcreatekeyex)|Belirtilen kayıt defteri anahtarı oluşturur ve bir işlem ile ilişkilendirir. Anahtar zaten varsa, işlev, açar.|  
|[RegDeleteKey](#regdeletekey)|Bir alt anahtarı ve değerleri kayıt defterinde belirtilen platforma özgü görünümünden hizmetteki bir işlem olarak siler.|  
|[RegOpenKeyEx](#regopenkeyex)|Belirtilen kayıt defteri anahtarı açar ve bir işlem ile ilişkilendirir.|  
|[Geri alma](#rollback)|İşlem geri alınamaz istek sayısı.|  
|[SetFileAttributes](#setfileattributes)|Bir dosya veya dizin özniteliklerini hizmetteki bir işlem olarak ayarlar.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[m_bFallback](#m_bfallback)|`TRUE`geri dönüş destekleniyorsa; `FALSE` Aksi takdirde.|  
|[m_hTransaction](#m_htransaction)|İşlem tanıtıcısı.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [ATL::CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atltransactionmanager.h  
  
##  <a name="dtor"></a>~ CAtlTransactionManager  
 CAtlTransactionManager yıkıcı.  
  
```
virtual ~CAtlTransactionManager();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Normal işlemde işlem otomatik olarak kaydedilen ve kapatılır. Yıkıcı bir özel durum geriye doğru izleme sırasında çağrılırsa, işlem geri alınamaz ve kapalı.  
  
##  <a name="catltransactionmanager"></a>CAtlTransactionManager  
 CAtlTransactionManager Oluşturucusu.  
  
```
CAtlTransactionManager(BOOL bFallback = TRUE, BOOL bAutoCreateTransaction = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bFallback`  
 `TRUE`Destek geri dönüş gösterir. İşlenen işlevi başarısız olursa sınıfı otomatik olarak "işlem temelli olmayan" işlevi çağırır. `FALSE`hiçbir "temel" çağrıları gösterir.  
  
 `bAutoCreateTransaction`  
 `TRUE`hareket işleyicisi oluşturucuda otomatik olarak oluşturulan gösterir. `FALSE`olmadığını gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="close"></a>Kapat  
 İşlem tanıtıcısı kapatır.  
  
```
inline BOOL Close();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sarmalayıcı çağırır `CloseHandle` işlevi. Yöntem yıkıcı otomatik olarak çağrılır.  
  
##  <a name="commit"></a>Tamamlama  
 İşlem tamamlanan istek sayısı.  
  
```
inline BOOL Commit();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sarmalayıcı çağırır `CommitTransaction` işlevi. Yöntem yıkıcı otomatik olarak çağrılır.  
  
##  <a name="create"></a>Oluşturma  
 İşlem tanıtıcısı oluşturur.  
  
```
inline BOOL Create();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sarmalayıcı çağırır `CreateTransaction` işlevi. Bunun için denetleyin  
  
##  <a name="createfile"></a>CreateFile  
 Oluşturur veya bir dosya, dosya akışı ya da dizin hizmetteki bir işlem olarak açar.  
  
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
 `lpFileName`  
 Açılan veya oluşturulacak bir nesne adı.  
  
 `dwDesiredAccess`  
 Okuma, yazma, hem veya hiçbiri (sıfır) özetlenebilir nesne erişimi. GENERIC_READ, GENERIC_WRITE veya her ikisi de en yaygın kullanılan değerler şunlardır: GENERIC_READ &#124; GENERIC_WRITE.  
  
 `dwShareMode`  
 Paylaşım modu okuma, yazma, her ikisi de olabilir, silme, bunların tümü veya hiçbiri bir nesnesinin: 0, FILE_SHARE_DELETE, FILE_SHARE_READ, FILE_SHARE_WRITE.  
  
 `lpSecurityAttributes`  
 Bir işaretçi SECURITY_ATTRIBUTES yapısına bir isteğe bağlı güvenlik tanımlayıcısı içerir ve ayrıca alt işlemleri tarafından döndürülen tanıtıcı devralınan olup olmadığını belirler. Parametre olabilir `NULL`.  
  
 `dwCreationDisposition`  
 Mevcut ve mevcut olmayan dosyalar üzerinde işlem yapmak için bir eylem. Bu parametre birleştirilemez şu değerlerden biri olmalıdır: CREATE_ALWAYS, CREATE_NEW, OPEN_ALWAYS, OPEN_EXISTING veya TRUNCATE_EXISTING.  
  
 `dwFlagsAndAttributes`  
 Dosya özniteliklerini ve bayraklar. Bu parametre, kullanılabilir bir dosya öznitelikleri (FILE_ATTRIBUTE_ *) herhangi bir birleşimini içerebilir. Diğer tüm dosya öznitelikleri FILE_ATTRIBUTE_NORMAL geçersiz kılar. Bu parametre bayrakları birleşimlerini de içerebilir (FILE_FLAG_\*) modları ve diğer özel amaçlı bayraklar davranışı ara belleğe almanın daha fazla denetim için erişim. Bunlar herhangi FILE_ATTRIBUTE_ ile birleştirerek\* değerleri.  
  
 `hTemplateFile`  
 Sağ GENERIC_READ erişimi olan bir şablon dosyası için geçerli bir tanıtıcı. Şablon dosyası, dosya öznitelikleri ve genişletilmiş öznitelikleri oluşturulmakta olan sağlar. Bu parametre olabilir `NULL`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesne erişmek için kullanılan bir işleyici döner.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sarmalayıcı çağırır `CreateFileTransacted` işlevi.  
  
##  <a name="deletefile"></a>DeleteFile  
 Varolan bir dosyanın hizmetteki bir işlem olarak siler.  
  
```
inline BOOL DeleteFile(LPCTSTR lpFileName);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpFileName`  
 Silinecek dosyasının adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sarmalayıcı çağırır `DeleteFileTransacted` işlevi.  
  
##  <a name="findfirstfile"></a>FindFirstFile  
 Bir dosya veya alt dizin için bir dizin hizmetteki bir işlem olarak arar.  
  
```
inline HANDLE FindFirstFile(
  LPCTSTR lpFileName,
  WIN32_FIND_DATA* pNextInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpFileName`  
 Dizin veya yolu ve aranacak dosya adı. Bu parametre bir yıldız işareti (*) veya bir soru işareti () gibi joker karakterler içerebilir.  
  
 `pNextInfo`  
 Bir işaretçi WIN32_FIND_DATA yapısına bulunan dosya veya alt hakkındaki bilgileri alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa, dönüş değeri bir sonraki çağrı için kullanılan bir arama işleyicisidir `FindNextFile` veya `FindClose`. İşlevi başarısız olduğunda veya arama dizesinde dosyaları bulmak başarısız olursa `lpFileName` parametresi, dönüş değeri INVALID_HANDLE_VALUE bağlıdır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sarmalayıcı çağırır `FindFirstFileTransacted` işlevi.  
  
##  <a name="getfileattributes"></a>GetFileAttributes  
 Belirtilen dosya veya dizin dosya sistemi özniteliklerini hizmetteki bir işlem olarak alır.  
  
```
inline DWORD GetFileAttributes(LPCTSTR lpFileName);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpFileName`  
 Dosya veya dizin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sarmalayıcı çağırır `GetFileAttributesTransacted` işlevi.  
  
##  <a name="getfileattributesex"></a>GetFileAttributesEx  
 Belirtilen dosya veya dizin dosya sistemi özniteliklerini hizmetteki bir işlem olarak alır.  
  
```
inline BOOL GetFileAttributesEx(
    LPCTSTR lpFileName,
    GET_FILEEX_INFO_LEVELS fInfoLevelId,
    LPVOID lpFileInformation);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpFileName`  
 Dosya veya dizin adı.  
  
 `fInfoLevelId`  
 Öznitelik bilgileri almak için düzeyi.  
  
 `lpFileInformation`  
 Öznitelik bilgileri aldığı bir arabellek için bir işaretçi. Bu belleğe depolanan öznitelik bilgileri türü değeri tarafından belirlenir `fInfoLevelId`. Varsa `fInfoLevelId` parametredir GetFileExInfoStandard sonra bu parametre bir WIN32_FILE_ATTRIBUTE_DATA yapısına işaret eder.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sarmalayıcı çağırır `GetFileAttributesTransacted` işlevi.  
  
##  <a name="gethandle"></a>GetHandle  
 İşlem tanıtıcısı döndürür.  
  
```
HANDLE GetHandle() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir sınıf için işlem tanıtıcısı döndürür. Döndürür `NULL` varsa `CAtlTransactionManager` için bir tanıtıcı bağlı değil.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isfallback"></a>IsFallback  
 Geri dönüş çağrılarının etkinleştirilip etkinleştirilmediğini belirler.  
  
```
BOOL IsFallback() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `TRUE` sınıfı geri dönüş çağrıları destekler. `FALSE`Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_bfallback"></a>m_bFallback  
 `TRUE`geri dönüş destekleniyorsa; `FALSE` Aksi takdirde.  
  
```
BOOL m_bFallback;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_htransaction"></a>m_hTransaction  
 İşlem tanıtıcısı.  
  
```
HANDLE m_hTransaction;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="movefile"></a>MoveFile  
 Varolan bir dosya veya alt öğelerini hizmetteki bir işlem olarak dahil olmak üzere bir dizin taşır.  
  
```
inline BOOL MoveFile(LPCTSTR lpOldFileName, LPCTSTR lpNewFileName);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpOldFileName`  
 Var olan dosya veya dizin yerel bilgisayardaki geçerli adı.  
  
 `lpNewFileName`  
 Dosya veya dizin için yeni adı. Bu ad zaten mevcut olmamalıdır. Yeni bir dosya bir başka bir dosya sistemi veya sürücüde olabilir. Yeni bir dizin aynı sürücüde olmalıdır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sarmalayıcı çağırır `MoveFileTransacted` işlevi.  
  
##  <a name="regcreatekeyex"></a>RegCreateKeyEx  
 Belirtilen kayıt defteri anahtarı oluşturur ve bir işlem ile ilişkilendirir. Anahtar zaten varsa, işlev, açar.  
  
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
 `hKey`  
 Bir kayıt defteri anahtarı için bir tanıtıcı.  
  
 `lpSubKey`  
 Bu işlev açar veya oluşturur bir alt anahtar adı.  
  
 `dwReserved`  
 Bu parametre ayrılmıştır ve sıfır olmalıdır.  
  
 `lpClass`  
 Bu anahtar kullanıcı tanımlı sınıfı. Bu parametre yoksayılabilir. Bu parametre NULL olabilir.  
  
 `dwOptions`  
 Bu parametre aşağıdaki değerlerden biri olabilir: REG_OPTION_BACKUP_RESTORE, REG_OPTION_NON_VOLATILE veya REG_OPTION_VOLATILE.  
  
 `samDesired`  
 Anahtar için erişim haklarını belirtir maskesi.  
  
 `lpSecurityAttributes`  
 Alt işlemleri tarafından döndürülen tanıtıcı devralınan olup olmadığını belirleyen bir SECURITY_ATTRIBUTES yapısına yönelik işaretçinin. Varsa `lpSecurityAttributes` olan `NULL`, tanıtıcı devralındı.  
  
 `phkResult`  
 Bir işaretçi bir değişkene açılan ya da oluşturulan anahtarı için bir tanıtıcı alır. Anahtar önceden tanımlanmış kayıt defteri anahtarlarından birini değilse, çağrı `RegCloseKey` tanıtıcı kullanmayı bitirdikten sonra çalışmaz.  
  
 `lpdwDisposition`  
 Aşağıdaki değerlendirme değerlerinden birini alan bir değişken için bir işaretçi: REG_CREATED_NEW_KEY veya REG_OPENED_EXISTING_KEY.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa, dönüş değeri ERROR_SUCCESS ' dir. İşlev başarısız olursa, dönüş değeri Winerror.h'de içinde tanımlanan bir sıfır olmayan hata kodudur.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sarmalayıcı çağırır `RegCreateKeyTransacted` işlevi.  
  
##  <a name="regdeletekey"></a>RegDeleteKey  
 Bir alt anahtarı ve değerleri kayıt defterinde belirtilen platforma özgü görünümünden hizmetteki bir işlem olarak siler.  
  
```
inline LSTATUS RegDeleteKeyEx(HKEY hKey, LPCTSTR lpSubKey);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`hKey`|Bir kayıt defteri anahtarı için bir tanıtıcı.|  
|`lpSubKey`|Silinecek anahtarın adı.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa, dönüş değeri ERROR_SUCCESS ' dir. İşlev başarısız olursa, dönüş değeri Winerror.h'de içinde tanımlanan bir sıfır olmayan hata kodudur.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sarmalayıcı çağırır `RegDeleteKeyTransacted` işlevi.  
  
##  <a name="regopenkeyex"></a>RegOpenKeyEx  
 Belirtilen kayıt defteri anahtarı açar ve bir işlem ile ilişkilendirir.  
  
```
inline LSTATUS RegOpenKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD ulOptions,
    REGSAM samDesired,
    PHKEY phkResult);
```  
  
### <a name="parameters"></a>Parametreler  
 `hKey`  
 Bir kayıt defteri anahtarı için bir tanıtıcı.  
  
 `lpSubKey`  
 Açılması için kayıt defteri alt anahtarı adı.  
  
 `ulOptions`  
 Bu parametre ayrılmıştır ve sıfır olmalıdır.  
  
 `samDesired`  
 Anahtar için erişim haklarını belirtir maskesi.  
  
 `phkResult`  
 Bir işaretçi bir değişkene açılan ya da oluşturulan anahtarı için bir tanıtıcı alır. Anahtar önceden tanımlanmış kayıt defteri anahtarlarından birini değilse, çağrı `RegCloseKey` tanıtıcı kullanmayı bitirdikten sonra çalışmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa, dönüş değeri ERROR_SUCCESS ' dir. İşlev başarısız olursa, dönüş değeri Winerror.h'de içinde tanımlanan bir sıfır olmayan hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sarmalayıcı çağırır `RegOpenKeyTransacted` işlevi.  
  
##  <a name="rollback"></a>Geri alma  
 İşlem geri alınamaz istek sayısı.  
  
```
inline BOOL Rollback();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sarmalayıcı çağırır `RollbackTransaction` işlevi.  
  
##  <a name="setfileattributes"></a>SetFileAttributes  
 Bir dosya veya dizin özniteliklerini hizmetteki bir işlem olarak ayarlar.  
  
```
inline BOOL SetFileAttributes(LPCTSTR lpFileName, DWORD dwAttributes);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpFileName`  
 Dosya veya dizin adı.  
  
 `dwAttributes`  
 Dosya için ayarlanacak dosya öznitelikleri. Daha fazla bilgi için bkz: [SetFileAttributesTransacted](http://go.microsoft.com/fwlink/p/?linkid=158699).  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sarmalayıcı çağırır `SetFileAttributesTransacted` işlevi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL COM Masaüstü Bileşenleri](../../atl/atl-com-desktop-components.md)
