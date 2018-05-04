---
title: CTokenGroups sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CTokenGroups
- ATLSECURITY/ATL::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::Add
- ATLSECURITY/ATL::CTokenGroups::Delete
- ATLSECURITY/ATL::CTokenGroups::DeleteAll
- ATLSECURITY/ATL::CTokenGroups::GetCount
- ATLSECURITY/ATL::CTokenGroups::GetLength
- ATLSECURITY/ATL::CTokenGroups::GetPTOKEN_GROUPS
- ATLSECURITY/ATL::CTokenGroups::GetSidsAndAttributes
- ATLSECURITY/ATL::CTokenGroups::LookupSid
dev_langs:
- C++
helpviewer_keywords:
- CTokenGroups class
ms.assetid: 2ab08076-4b08-4487-bc70-ec6dee304190
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ccf73cdeac0e7522551c6ddb7bef6b0122297ca
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ctokengroups-class"></a>CTokenGroups sınıfı
Bu sınıf için sarmalayıcı, **TOKEN_GROUPS** yapısı.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CTokenGroups
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTokenGroups::CTokenGroups](#ctokengroups)|Oluşturucu.|  
|[CTokenGroups:: ~ CTokenGroups](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTokenGroups::Add](#add)|Ekler bir `CSid` veya varolan **TOKEN_GROUPS** için yapı `CTokenGroups` nesnesi.|  
|[CTokenGroups::Delete](#delete)|Siler bir `CSid` ve ilişkili öznitelikleri gelen `CTokenGroups` nesnesi.|  
|[CTokenGroups::DeleteAll](#deleteall)|Tüm siler `CSid` nesneleri ve bunların ilişkili öznitelikleri `CTokenGroups` nesnesi.|  
|[CTokenGroups::GetCount](#getcount)|Sayısını döndürür `CSid` nesneleri ve ilişkili öznitelikleri bulunan **CTokenGroups** nesnesi.|  
|[CTokenGroups::GetLength](#getlength)|Boyutu döndüren `CTokenGroups` nesnesi.|  
|[CTokenGroups::GetPTOKEN_GROUPS](#getptoken_groups)|Bir işaretçi alır **TOKEN_GROUPS** yapısı.|  
|[CTokenGroups::GetSidsAndAttributes](#getsidsandattributes)|Alır `CSid` nesneleri ve öznitelikleri ait `CTokenGroups` nesnesi.|  
|[CTokenGroups::LookupSid](#lookupsid)|İle ilişkili öznitelikleri alır bir `CSid` nesnesi.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTokenGroups::operator const TOKEN_GROUPS *](#operator_const_token_groups__star)|Atamalar `CTokenGroups` gösteren bir işaretçi nesnesine **TOKEN_GROUPS** yapısı.|  
|[CTokenGroups::operator =](#operator_eq)|Atama işleci.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir [erişim belirteci](http://msdn.microsoft.com/library/windows/desktop/aa374909) bir işlem veya iş parçacığı güvenlik bağlamında açıklayan ve bir Windows sisteminde oturum açmış her kullanıcı için ayrılan bir nesnedir.  
  
 **CTokenGroups** için sarmalayıcı sınıftır [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) yapısı, bir erişim belirteci grup güvenlik tanımlayıcılarını (SID'ler) hakkında bilgi içeren.  
  
 Erişim denetimi modeli Windows giriş için bkz: [erişim denetimi](http://msdn.microsoft.com/library/windows/desktop/aa374860) Windows SDK'sındaki.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsecurity.h  
  
##  <a name="add"></a>  CTokenGroups::Add  
 Ekler bir `CSid` veya varolan **TOKEN_GROUPS** için yapı `CTokenGroups` nesnesi.  
  
```
void Add(const CSid& rSid, DWORD dwAttributes) throw(... );  
void Add(const TOKEN_GROUPS& rTokenGroups) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rSid`  
 A [CSID](../../atl/reference/csid-class.md) nesnesi.  
  
 `dwAttributes`  
 İlişkilendirmek için öznitelikler `CSid` nesnesi.  
  
 *rTokenGroups*  
 A [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemler bir veya daha fazla Ekle `CSid` nesneleri ve bunların ilişkili öznitelikleri `CTokenGroups` nesnesi.  
  
##  <a name="ctokengroups"></a>  CTokenGroups::CTokenGroups  
 Oluşturucu.  
  
```
CTokenGroups() throw();
CTokenGroups(const CTokenGroups& rhs) throw(... );  
CTokenGroups(const TOKEN_GROUPS& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rhs`  
 `CTokenGroups` Nesne veya [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) yapısı oluşturmak hangi `CTokenGroups` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 `CTokenGroups` Nesne isteğe bağlı olarak kullanılarak oluşturulabilir bir **TOKEN_GROUPS** yapısı veya önceden tanımlanmış `CTokenGroups` nesnesi.  
  
##  <a name="dtor"></a>  CTokenGroups:: ~ CTokenGroups  
 Yok Edicisi.  
  
```
virtual ~CTokenGroups() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yok Edicisi ayrılan tüm kaynakları serbest bırakır.  
  
##  <a name="delete"></a>  CTokenGroups::Delete  
 Siler bir `CSid` ve ilişkili öznitelikleri gelen `CTokenGroups` nesnesi.  
  
```
bool Delete(const CSid& rSid) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `rSid`  
 [CSID](../../atl/reference/csid-class.md) nesne için güvenlik tanımlayıcısı (SID) ve öznitelikleri kaldırılması gerekir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsa true değerini döndürür `CSid` yanlış aksi kaldırılmıştır.  
  
##  <a name="deleteall"></a>  CTokenGroups::DeleteAll  
 Tüm siler `CSid` nesneleri ve bunların ilişkili öznitelikleri `CTokenGroups` nesnesi.  
  
```
void DeleteAll() throw();
```  
  
##  <a name="getcount"></a>  CTokenGroups::GetCount  
 Sayısını döndürür `CSid` içinde yer alan nesneler `CTokenGroups`.  
  
```
UINT GetCount() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sayısını döndürür [CSID](../../atl/reference/csid-class.md) nesneleri ve bunların ilişkili öznitelikleri bulunan `CTokenGroups` nesnesi.  
  
##  <a name="getlength"></a>  CTokenGroups::GetLength  
 Boyutu döndüren **CTokenGroup** nesnesi.  
  
```
UINT GetLength() const throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Toplam boyutu döndüren **CTokenGroup** nesnesinde bayt sayısı.  
  
##  <a name="getptoken_groups"></a>  CTokenGroups::GetPTOKEN_GROUPS  
 Bir işaretçi alır **TOKEN_GROUPS** yapısı.  
  
```
const TOKEN_GROUPS* GetPTOKEN_GROUPS() const throw(...);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi alır [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) ait yapısı `CTokenGroups` erişim belirteci nesnesi.  
  
##  <a name="getsidsandattributes"></a>  CTokenGroups::GetSidsAndAttributes  
 Alır `CSid` nesneleri ve (isteğe bağlı) ait öznitelikleri `CTokenGroups` nesnesi.  
  
```
void GetSidsAndAttributes(
    CSid::CSidArray* pSids,
    CAtlArray<DWORD>* pAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pSids`  
 Bir dizi işaretçi [CSID](../../atl/reference/csid-class.md) nesneleri.  
  
 `pAttributes`  
 DWORD dizisi işaretçi. Bu parametre atlanırsa ya da NULL ise, öznitelikleri alınmamış.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tüm Numaralandırılacak `CSid` içinde yer alan nesneler `CTokenGroups` nesne ve bunları ve (isteğe bağlı) öznitelik bayrakları dizi nesneleri yerleştirin.  
  
##  <a name="lookupsid"></a>  CTokenGroups::LookupSid  
 İle ilişkili öznitelikleri alır bir `CSid` nesnesi.  
  
```
bool LookupSid(  
    const CSid& rSid,
    DWORD* pdwAttributes = NULL) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `rSid`  
 [CSID](../../atl/reference/csid-class.md) nesnesi.  
  
 `pdwAttributes`  
 Kabul edeceği bir DWORD işaretçi `CSid` nesnenin öznitelik. Belirtilmemişse veya boş ise, öznitelik alınmayacak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsa true değerini döndürür `CSid` bulunursa, false Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarı `pdwAttributes` için NULL varlığını onaylayan bir yol sağlar `CSid` öznitelik erişme olmadan. Bu yöntem erişim hakları denetlemek için kullanılmamalıdır olduğunu unutmayın. Uygulamaların yerine kullanması gereken [CAccessToken::CheckTokenMembership](../../atl/reference/caccesstoken-class.md#checktokenmembership) yöntemi.  
  
##  <a name="operator_eq"></a>  CTokenGroups::operator =  
 Atama işleci.  
  
```
CTokenGroups& operator= (const TOKEN_GROUPS& rhs) throw(...);  
CTokenGroups& operator= (const CTokenGroups& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rhs`  
 `CTokenGroups` Nesne veya [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) atamak için yapısı `CTokenGroups` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş döndürür `CTokenGroups` nesnesi.  
  
##  <a name="operator_const_token_groups__star"></a>  CTokenGroups::operator const TOKEN_GROUPS *  
 Bir işaretçi bir değere bıraktığı **TOKEN_GROUPS** yapısı.  
  
```  
operator const TOKEN_GROUPS *() const throw(...);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir işaretçi bir değere bıraktığı [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) yapısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Güvenliği örneği](../../visual-cpp-samples.md)   
 [CSID sınıfı](../../atl/reference/csid-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
