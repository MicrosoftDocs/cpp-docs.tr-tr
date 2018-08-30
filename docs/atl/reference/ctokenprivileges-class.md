---
title: CTokenPrivileges sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges::CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges::Add
- ATLSECURITY/ATL::CTokenPrivileges::Delete
- ATLSECURITY/ATL::CTokenPrivileges::DeleteAll
- ATLSECURITY/ATL::CTokenPrivileges::GetCount
- ATLSECURITY/ATL::CTokenPrivileges::GetDisplayNames
- ATLSECURITY/ATL::CTokenPrivileges::GetLength
- ATLSECURITY/ATL::CTokenPrivileges::GetLuidsAndAttributes
- ATLSECURITY/ATL::CTokenPrivileges::GetNamesAndAttributes
- ATLSECURITY/ATL::CTokenPrivileges::GetPTOKEN_PRIVILEGES
- ATLSECURITY/ATL::CTokenPrivileges::LookupPrivilege
dev_langs:
- C++
helpviewer_keywords:
- CTokenPrivileges class
ms.assetid: 89590105-f001-4014-870d-142926091231
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 23c8776e462c2b275b0c7620e01b4bc82e7ad7ed
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43195750"
---
# <a name="ctokenprivileges-class"></a>CTokenPrivileges sınıfı
Bu sınıf için bir sarmalayıcı olan `TOKEN_PRIVILEGES` yapısı.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CTokenPrivileges
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTokenPrivileges::CTokenPrivileges](#ctokenprivileges)|Oluşturucu.|  
|[CTokenPrivileges:: ~ CTokenPrivileges](#dtor)|Yıkıcı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTokenPrivileges::Add](#add)|Bir veya daha fazla ayrıcalık ekler `CTokenPrivileges` nesne.|  
|[CTokenPrivileges::Delete](#delete)|Bir ayrıcalığı siler `CTokenPrivileges` nesne.|  
|[CTokenPrivileges::DeleteAll](#deleteall)|Tüm ayrıcalıklarından siler `CTokenPrivileges` nesne.|  
|[CTokenPrivileges::GetCount](#getcount)|Ayrıcalık girişleri döndürür `CTokenPrivileges` nesne.|  
|[CTokenPrivileges::GetDisplayNames](#getdisplaynames)|Alır görünen adlar bulunan ayrıcalıkların `CTokenPrivileges` nesne.|  
|[CTokenPrivileges::GetLength](#getlength)|Arabellek boyutu barındırmak için gereken bayt cinsinden döndürür `TOKEN_PRIVILEGES` yapısını temsil ettiği `CTokenPrivileges` nesne.|  
|[CTokenPrivileges::GetLuidsAndAttributes](#getluidsandattributes)|Yerel olarak benzersiz tanımlayıcıları (Luıd'leri) ve öznitelik bayraklarını alır `CTokenPrivileges` nesne.|  
|[CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes)|Ayrıcalık adlarını ve öznitelik bayraklarını alır `CTokenPrivileges` nesne.|  
|[CTokenPrivileges::GetPTOKEN_PRIVILEGES](#getptoken_privileges)|Bir işaretçi döndürür `TOKEN_PRIVILEGES` yapısı.|  
|[CTokenPrivileges::LookupPrivilege](#lookupprivilege)|Verilen ayrıcalık adıyla ilişkili özniteliği alır.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTokenPrivileges::operator const TOKEN_PRIVILEGES *](#operator_const_token_privileges__star)|Bir işaretçi değerine çevirir `TOKEN_PRIVILEGES` yapısı.|  
|[CTokenPrivileges::operator =](#operator_eq)|Atama işleci.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir [erişim belirteci](/windows/desktop/SecAuthZ/access-tokens) bir işlem veya iş parçacığı güvenlik bağlamı açıklayan ve Windows sisteminde oturum açmış her kullanıcı için ayrılan bir nesnedir.  
  
 Erişim belirteci, her kullanıcıya verilen çeşitli güvenlik ayrıcalıkları tanımlamak için kullanılır. Yerel olarak benzersiz bir tanımlayıcı adlı bir 64-bit sayısı ayrıcalık oluşur ( [LUID'ini](/windows/desktop/api/winnt/ns-winnt-_luid)) ve bir tanımlayıcı dizesi.  
  
 `CTokenPrivileges` İçin bir sarmalayıcı sınıftır [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges) yapısı ve 0 veya daha fazla ayrıcalık içerir. Silinmiş veya sorgulanan sağlanan sınıfı yöntemleri kullanarak ayrıcalıkları eklenebilir.  
  
 Windows, erişim denetimi modeli için bir giriş için bkz [erişim denetimi](/windows/desktop/SecAuthZ/access-control) Windows SDK.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsecurity.h  
  
##  <a name="add"></a>  CTokenPrivileges::Add  
 Bir veya daha fazla ayrıcalık ekler `CTokenPrivileges` erişim belirteci nesnesi.  
  
```
bool Add(LPCTSTR pszPrivilege, bool bEnable) throw(...);  
void Add(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 *pszPrivilege*  
 Null ile sonlandırılmış WINNT içinde tanımlanan ayrıcalık adını belirten bir dize işaretçisi. H üst bilgi dosyası.  
  
 *bSistemlerde*  
 TRUE ise ayrıcalık etkinleştirilir. False ise, ayrıcalık devre dışı bırakıldı.  
  
 *rPrivileges*  
 Başvuru bir [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges) yapısı. Öznitelikler ve ayrıcalıkları bu yapısından kopyalanır ve eklenen `CTokenPrivileges` nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem ilk formu ayrıcalıkları başarıyla eklendi, yanlış Aksi takdirde true değerini döndürür.  
  
##  <a name="ctokenprivileges"></a>  CTokenPrivileges::CTokenPrivileges  
 Oluşturucu.  
  
```
CTokenPrivileges() throw();
CTokenPrivileges(const CTokenPrivileges& rhs) throw(... );  
CTokenPrivileges(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 *Sol*  
 `CTokenPrivileges` Yeni nesneye atamak için nesne.  
  
 *rPrivileges*  
 [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges) yeni atamak yapısı `CTokenPrivileges` nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 `CTokenPrivileges` Nesne isteğe bağlı olarak oluşturulabilir kullanarak bir `TOKEN_PRIVILEGES` yapısı veya önceden tanımlanmış `CTokenPrivileges` nesne.  
  
##  <a name="dtor"></a>  CTokenPrivileges:: ~ CTokenPrivileges  
 Yıkıcı.  
  
```
virtual ~CTokenPrivileges() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yok edici ayrılan tüm kaynakları serbest bırakır.  
  
##  <a name="delete"></a>  CTokenPrivileges::Delete  
 Bir ayrıcalığı siler `CTokenPrivileges` erişim belirteci nesnesi.  
  
```
bool Delete(LPCTSTR pszPrivilege) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *pszPrivilege*  
 Null ile sonlandırılmış WINNT içinde tanımlanan ayrıcalık adını belirten bir dize işaretçisi. H üst bilgi dosyası. Örneğin, bu parametre sabiti SE_SECURITY_NAME veya karşılık gelen dize, "SeSecurityPrivilege." belirtebilirsiniz  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrıcalık Aksi halde başarıyla silindi, false ise, true döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, kısıtlı belirteçleri oluşturmak için bir araç olarak kullanışlıdır.  
  
##  <a name="deleteall"></a>  CTokenPrivileges::DeleteAll  
 Tüm ayrıcalıklarından siler `CTokenPrivileges` erişim belirteci nesnesi.  
  
```
void DeleteAll() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 İçindeki tüm ayrıcalıkları siler `CTokenPrivileges` erişim belirteci nesnesi.  
  
##  <a name="getdisplaynames"></a>  CTokenPrivileges::GetDisplayNames  
 Alır görünen adlar bulunan ayrıcalıkların `CTokenPrivileges` erişim belirteci nesnesi.  
  
```
void GetDisplayNames(CNames* pDisplayNames) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 *pDisplayNames*  
 Bir dizi işaretçi `CString` nesneleri. `CNames` typedef tanımlanır: `CTokenPrivileges::CAtlArray<CString>`.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametre `pDisplayNames` dizisi işaretçisidir `CString` bulunan ayrıcalıkların karşılık gelen görünen adlarını alacak nesneleri `CTokenPrivileges` nesne. Bu yöntem yalnızca WINNT tanımlanmış ayrıcalıklar bölümünde belirtilen ayrıcalıkları için görünen adları alır. H  
  
 Bu yöntem görüntülenebilir adını alır: öznitelik adı SE_REMOTE_SHUTDOWN_NAME ise, örneğin, görüntülenebilen "Uzak sistemden kapatmayı zorla". adıdır Sistem adını almak için kullanın [CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes).  
  
##  <a name="getcount"></a>  CTokenPrivileges::GetCount  
 Ayrıcalık girişleri döndürür `CTokenPrivileges` nesne.  
  
```
UINT GetCount() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrıcalıkları yer alan sayısını döndürür `CTokenPrivileges` nesne.  
  
##  <a name="getlength"></a>  CTokenPrivileges::GetLength  
 Uzunluğunu döndürür `CTokenPrivileges` nesne.  
  
```
UINT GetLength() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Barındırmak için gereken bayt sayısını döndüren bir `TOKEN_PRIVILEGES` yapısını temsil ettiği `CTokenPrivileges` tüm içerdiği ayrıcalık girişleri de dahil olmak üzere nesne.  
  
##  <a name="getluidsandattributes"></a>  CTokenPrivileges::GetLuidsAndAttributes  
 Yerel olarak benzersiz tanımlayıcıları (Luıd'leri) ve öznitelik bayraklarını alır `CTokenPrivileges` nesne.  
  
```
void GetLuidsAndAttributes(
    CLUIDArray* pPrivileges,
    CAttributes* pAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 *pPrivileges*  
 Bir dizi işaretçi [LUID'ini](/windows/desktop/api/winnt/ns-winnt-_luid) nesneleri. `CLUIDArray` typedef olarak tanımlanan `CAtlArray<LUID> CLUIDArray`.  
  
 *pAttributes*  
 DWORD nesnelerin dizisine yönelik işaretçi. Bu parametre belirtilmemişse veya NULL ise, öznitelikleri alınmamış. `CAttributes` typedef olarak tanımlanan `CAtlArray <DWORD> CAttributes`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem bulunan ayrıcalıkların tümünü listeleyeceksiniz `CTokenPrivileges` erişim belirteci nesne ve dizi nesnelerine tek tek Luıd'leri ve (isteğe bağlı olarak) özniteliği bayrakları yerleştirin.  
  
##  <a name="getnamesandattributes"></a>  CTokenPrivileges::GetNamesAndAttributes  
 Ad ve öznitelik bayrakları alır `CTokenPrivileges` nesne.  
  
```
void GetNamesAndAttributes(
    CNames* pNames,
    CAttributes* pAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 *pNames*  
 Bir dizi işaretçi `CString` nesneleri. `CNames` typedef olarak tanımlanan `CAtlArray <CString> CNames`.  
  
 *pAttributes*  
 DWORD nesnelerin dizisine yönelik işaretçi. Bu parametre belirtilmemişse veya NULL ise, öznitelikleri alınmamış. `CAttributes` typedef olarak tanımlanan `CAtlArray <DWORD> CAttributes`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem bulunan ayrıcalıkların tümünü listeleyeceksiniz `CTokenPrivileges` nesne, dizi nesnelerini adı ve (isteğe bağlı olarak) özniteliği bayrakları yerleştirme.  
  
 Bu yöntem görüntülenebilir adı yerine, öznitelik adı alır: öznitelik adı SE_REMOTE_SHUTDOWN_NAME gibi sistem adı "SeRemoteShutdownPrivilege." ise, Annotatable adı almak için yöntemi kullanın. [CTokenPrivileges::GetDisplayNames](#getdisplaynames).  
  
##  <a name="getptoken_privileges"></a>  CTokenPrivileges::GetPTOKEN_PRIVILEGES  
 Bir işaretçi döndürür `TOKEN_PRIVILEGES` yapısı.  
  
```
const TOKEN_PRIVILEGES* GetPTOKEN_PRIVILEGES() const throw(...);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi döndürür [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges) yapısı.  
  
##  <a name="lookupprivilege"></a>  CTokenPrivileges::LookupPrivilege  
 Verilen ayrıcalık adıyla ilişkili özniteliği alır.  
  
```
bool LookupPrivilege(
    LPCTSTR pszPrivilege,
    DWORD* pdwAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 *pszPrivilege*  
 Null ile sonlandırılmış WINNT içinde tanımlanan ayrıcalık adını belirten bir dize işaretçisi. H üst bilgi dosyası. Örneğin, bu parametre sabiti SE_SECURITY_NAME veya karşılık gelen dize, "SeSecurityPrivilege." belirtebilirsiniz  
  
 *pdwAttributes*  
 İşaretçi bir değişkene özniteliklerini alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öznitelik, aksi halde başarıyla alındı, false ise, true döndürür.  
  
##  <a name="operator_eq"></a>  CTokenPrivileges::operator =  
 Atama işleci.  
  
```
CTokenPrivileges& operator= (const TOKEN_PRIVILEGES& rPrivileges) throw(...);  
CTokenPrivileges& operator= (const CTokenPrivileges& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 *rPrivileges*  
 [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges) atamak için yapı `CTokenPrivileges` nesne.  
  
 *Sol*  
 `CTokenPrivileges` Nesneye atamak için nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş döndürür `CTokenPrivileges` nesne.  
  
##  <a name="operator_const_token_privileges__star"></a>  CTokenPrivileges::operator const TOKEN_PRIVILEGES \*  
 Bir işaretçi değerine çevirir `TOKEN_PRIVILEGES` yapısı.  
  
```  
operator const TOKEN_PRIVILEGES *() const throw(...);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir işaretçi değerine çevirir [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges) yapısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Güvenliği örneği](../../visual-cpp-samples.md)   
 [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges)   
 [LUID'İNİ](/windows/desktop/api/winnt/ns-winnt-_luid)   
 [LUID_AND_ATTRIBUTES KONUSUNA](/windows/desktop/api/winnt/ns-winnt-_luid_and_attributes)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)   
 [Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
