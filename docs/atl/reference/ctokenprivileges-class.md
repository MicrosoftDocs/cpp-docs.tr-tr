---
title: "CTokenPrivileges sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
helpviewer_keywords: CTokenPrivileges class
ms.assetid: 89590105-f001-4014-870d-142926091231
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1b6a7d1c76b9ddb0aa555e8856f26da99611f553
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ctokenprivileges-class"></a>CTokenPrivileges sınıfı
Bu sınıf için sarmalayıcı, **TOKEN_PRIVILEGES** yapısı.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CTokenPrivileges
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTokenPrivileges::CTokenPrivileges](#ctokenprivileges)|Oluşturucu.|  
|[CTokenPrivileges:: ~ CTokenPrivileges](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTokenPrivileges::Add](#add)|Bir veya daha fazla ayrıcalık ekler `CTokenPrivileges` nesnesi.|  
|[CTokenPrivileges::Delete](#delete)|Bir ayrıcalığını siler `CTokenPrivileges` nesnesi.|  
|[CTokenPrivileges::DeleteAll](#deleteall)|Gelen tüm ayrıcalıkları siler `CTokenPrivileges` nesnesi.|  
|[CTokenPrivileges::GetCount](#getcount)|Ayrıcalık girişlerinde sayısını döndürür `CTokenPrivileges` nesnesi.|  
|[CTokenPrivileges::GetDisplayNames](#getdisplaynames)|Alır görünen adlar bulunan ayrıcalıkların `CTokenPrivileges` nesnesi.|  
|[CTokenPrivileges::GetLength](#getlength)|Arabellek boyutu tutmak için gereken bayt cinsinden döndürür **TOKEN_PRIVILEGES** yapısını temsil ettiği `CTokenPrivileges` nesnesi.|  
|[CTokenPrivileges::GetLuidsAndAttributes](#getluidsandattributes)|Yerel olarak benzersiz tanımlayıcısı (LUIDs) ve öznitelik bayraklarını alır `CTokenPrivileges` nesnesi.|  
|[CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes)|Öznitelik bayrakları kaldırır ve ayrıcalık adlarını alır `CTokenPrivileges` nesnesi.|  
|[CTokenPrivileges::GetPTOKEN_PRIVILEGES](#getptoken_privileges)|Bir işaretçi döndürür **TOKEN_PRIVILEGES** yapısı.|  
|[CTokenPrivileges::LookupPrivilege](#lookupprivilege)|Verilen ayrıcalık adıyla ilişkili özniteliği alır.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTokenPrivileges::operator const TOKEN_PRIVILEGES *](#operator_const_token_privileges__star)|Bir işaretçi bir değere bıraktığı **TOKEN_PRIVILEGES** yapısı.|  
|[CTokenPrivileges::operator =](#operator_eq)|Atama işleci.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir [erişim belirteci](http://msdn.microsoft.com/library/windows/desktop/aa374909) bir işlem veya iş parçacığı güvenlik bağlamında açıklayan ve Windows NT veya Windows 2000 sisteminde oturum açmış her kullanıcı için ayrılan bir nesnedir.  
  
 Erişim belirteci, her kullanıcı için çeşitli güvenlik ayrıcalıklarının açıklamak için kullanılır. Yerel olarak benzersiz bir tanımlayıcı olarak adlandırılan bir 64-bit sayısını ayrıcalık oluşur ( [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)) ve tanımlayıcısı dizesi.  
  
 `CTokenPrivileges` İçin sarmalayıcı sınıftır [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) yapısı ve 0 veya daha fazla ayrıcalık içerir. Silinmiş veya sorgulanan sağlanan sınıfı yöntemleri kullanarak ayrıcalık eklenebilir.  
  
 Erişim denetimi modeli Windows giriş için bkz: [erişim denetimi](http://msdn.microsoft.com/library/windows/desktop/aa374860) Windows SDK'sındaki.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsecurity.h  
  
##  <a name="add"></a>CTokenPrivileges::Add  
 Bir veya daha fazla ayrıcalık ekler `CTokenPrivileges` erişim belirteci nesnesi.  
  
```
bool Add(LPCTSTR pszPrivilege, bool bEnable) throw(...);  
void Add(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pszPrivilege`  
 İşaretçi null ile sonlandırılmış dizeye WINNT tanımlanan ayrıcalık adını belirtir. H üstbilgi dosyası.  
  
 `bEnable`  
 TRUE ise, ayrıcalık etkinleştirilir. False ayrıcalık devre dışı bırakılır.  
  
 `rPrivileges`  
 Başvuru bir [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) yapısı. Ayrıcalıklarını ve özniteliklerini bu yapısından kopyalanır ve eklenen `CTokenPrivileges` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntemin ilk form ayrıcalıkları başarıyla eklendi, false Aksi takdirde true değerini döndürür.  
  
##  <a name="ctokenprivileges"></a>CTokenPrivileges::CTokenPrivileges  
 Oluşturucu.  
  
```
CTokenPrivileges() throw();
CTokenPrivileges(const CTokenPrivileges& rhs) throw(... );  
CTokenPrivileges(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rhs`  
 `CTokenPrivileges` Nesne yeni nesneye atamak için.  
  
 `rPrivileges`  
 [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) yeni sunucuya atanacak yapı `CTokenPrivileges` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 `CTokenPrivileges` Nesne isteğe bağlı olarak kullanılarak oluşturulabilir bir **TOKEN_PRIVILEGES** yapısı veya önceden tanımlanmış `CTokenPrivileges` nesnesi.  
  
##  <a name="dtor"></a>CTokenPrivileges:: ~ CTokenPrivileges  
 Yok Edicisi.  
  
```
virtual ~CTokenPrivileges() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yok Edicisi ayrılan tüm kaynakları serbest bırakır.  
  
##  <a name="delete"></a>CTokenPrivileges::Delete  
 Bir ayrıcalığını siler `CTokenPrivileges` erişim belirteci nesnesi.  
  
```
bool Delete(LPCTSTR pszPrivilege) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pszPrivilege`  
 İşaretçi null ile sonlandırılmış dizeye WINNT tanımlanan ayrıcalık adını belirtir. H üstbilgi dosyası. Örneğin, bu parametre SE_SECURITY_NAME sabit veya karşılık gelen dize, "SeSecurityPrivilege." belirtebilirsiniz  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrıcalık Aksi halde başarıyla silindi, false ise, true döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, Windows 2000 kısıtlı belirteçleri oluşturmak için bir araç olarak kullanışlıdır.  
  
##  <a name="deleteall"></a>CTokenPrivileges::DeleteAll  
 Gelen tüm ayrıcalıkları siler `CTokenPrivileges` erişim belirteci nesnesi.  
  
```
void DeleteAll() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 İçinde yer alan tüm ayrıcalıkları siler `CTokenPrivileges` erişim belirteci nesnesi.  
  
##  <a name="getdisplaynames"></a>CTokenPrivileges::GetDisplayNames  
 Alır görünen adlar bulunan ayrıcalıkların `CTokenPrivileges` erişim belirteci nesnesi.  
  
```
void GetDisplayNames(CNames* pDisplayNames) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDisplayNames`  
 Bir dizi için bir işaretçi `CString` nesneleri. **CNames** typedef tanımlanır: **CTokenPrivileges::CAtlArray\<CString >**.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametre `pDisplayNames` gösteren bir işaretçidir bir dizi `CString` içinde yer alan ayrıcalıkları karşılık gelen görünen adları alacak nesneleri `CTokenPrivileges` nesnesi. Bu yöntem yalnızca WINNT tanımlanmış ayrıcalıklar bölümünde belirtilen ayrıcalıkları için görünen adları alır. H.  
  
 Bu yöntem görüntülenebilir adını alır: Örneğin, öznitelik adı SE_REMOTE_SHUTDOWN_NAME ise, "Uzak sistemden kapatmayı zorla". görüntülenebilir adı. Sistem adını almak için kullanın [CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes).  
  
##  <a name="getcount"></a>CTokenPrivileges::GetCount  
 Ayrıcalık girişlerinde sayısını döndürür `CTokenPrivileges` nesnesi.  
  
```
UINT GetCount() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrıcalıkları içinde yer alan sayısını döndürür `CTokenPrivileges` nesnesi.  
  
##  <a name="getlength"></a>CTokenPrivileges::GetLength  
 Uzunluğunu döndürür `CTokenPrivileges` nesnesi.  
  
```
UINT GetLength() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tutmak için gereken bayt sayısını döndürür bir **TOKEN_PRIVILEGES** yapısını temsil ettiği `CTokenPrivileges` tüm içerdiği ayrıcalık girdilerini de dahil olmak üzere nesne.  
  
##  <a name="getluidsandattributes"></a>CTokenPrivileges::GetLuidsAndAttributes  
 Yerel olarak benzersiz tanımlayıcısı (LUIDs) ve öznitelik bayraklarını alır `CTokenPrivileges` nesnesi.  
  
```
void GetLuidsAndAttributes(
    CLUIDArray* pPrivileges,
    CAttributes* pAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pPrivileges`  
 Bir dizi işaretçi [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261) nesneleri. **CLUIDArray** bir typedef olarak tanımlanan **CAtlArray\<LUID > CLUIDArray**.  
  
 `pAttributes`  
 DWORD nesnelerinin bir dizisi işaretçi. Bu parametre atlanırsa ya da NULL ise, öznitelikleri alınmamış. **CAttributes** bir typedef olarak tanımlanan **CAtlArray \<DWORD > CAttributes**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tüm bulunan ayrıcalıklarının Numaralandırılacak `CTokenPrivileges` erişim belirteci nesne ve tek tek LUIDs ve (isteğe bağlı) öznitelik bayrakları dizi nesneleri yerleştirin.  
  
##  <a name="getnamesandattributes"></a>CTokenPrivileges::GetNamesAndAttributes  
 Ad ve öznitelik bayraklarını alır `CTokenPrivileges` nesnesi.  
  
```
void GetNamesAndAttributes(
    CNames* pNames,
    CAttributes* pAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 *pNames*  
 Bir dizi işaretçi `CString` nesneleri. **CNames** bir typedef olarak tanımlanan **CAtlArray \<CString > CNAME'ler**.  
  
 `pAttributes`  
 DWORD nesnelerinin bir dizisi işaretçi. Bu parametre atlanırsa ya da NULL ise, öznitelikleri alınmamış. **CAttributes** bir typedef olarak tanımlanan **CAtlArray \<DWORD > CAttributes**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tüm bulunan ayrıcalıklarının Numaralandırılacak `CTokenPrivileges` adını ve (isteğe bağlı) öznitelik bayrakları dizi nesnelerine yerleştirmeyi nesnesi.  
  
 Bu yöntem görüntülenebilir adı yerine öznitelik adı alır: Örneğin, öznitelik adı SE_REMOTE_SHUTDOWN_NAME ise, sistem adı "SeRemoteShutdownPrivilege.". Görüntülenebilecek adı almak için yöntemi kullanın [CTokenPrivileges::GetDisplayNames](#getdisplaynames).  
  
##  <a name="getptoken_privileges"></a>CTokenPrivileges::GetPTOKEN_PRIVILEGES  
 Bir işaretçi döndürür **TOKEN_PRIVILEGES** yapısı.  
  
```
const TOKEN_PRIVILEGES* GetPTOKEN_PRIVILEGES() const throw(...);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi döndürür [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) yapısı.  
  
##  <a name="lookupprivilege"></a>CTokenPrivileges::LookupPrivilege  
 Verilen ayrıcalık adıyla ilişkili özniteliği alır.  
  
```
bool LookupPrivilege(
    LPCTSTR pszPrivilege,
    DWORD* pdwAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pszPrivilege`  
 İşaretçi null ile sonlandırılmış dizeye WINNT tanımlanan ayrıcalık adını belirtir. H üstbilgi dosyası. Örneğin, bu parametre SE_SECURITY_NAME sabit veya karşılık gelen dize, "SeSecurityPrivilege." belirtebilirsiniz  
  
 `pdwAttributes`  
 İşaretçi bir değişkene özniteliklerini alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öznitelik Aksi halde başarıyla alınırsa, false ise, true döndürür.  
  
##  <a name="operator_eq"></a>CTokenPrivileges::operator =  
 Atama işleci.  
  
```
CTokenPrivileges& operator= (const TOKEN_PRIVILEGES& rPrivileges) throw(...);  
CTokenPrivileges& operator= (const CTokenPrivileges& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rPrivileges`  
 [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) atamak için yapısı `CTokenPrivileges` nesnesi.  
  
 `rhs`  
 `CTokenPrivileges` Nesnesine atamak için nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş döndürür `CTokenPrivileges` nesnesi.  
  
##  <a name="operator_const_token_privileges__star"></a>CTokenPrivileges::operator const TOKEN_PRIVILEGES *  
 Bir işaretçi bir değere bıraktığı **TOKEN_PRIVILEGES** yapısı.  
  
```  
operator const TOKEN_PRIVILEGES *() const throw(...);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir işaretçi bir değere bıraktığı [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) yapısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Güvenliği örneği](../../visual-cpp-samples.md)   
 [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630)   
 [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)   
 [LUID_AND_ATTRIBUTES KONUSUNA](http://msdn.microsoft.com/library/windows/desktop/aa379263)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [Güvenlik genel işlevler](../../atl/reference/security-global-functions.md)
