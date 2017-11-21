---
title: "CDacl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDacl
- ATLSECURITY/ATL::CDacl
- ATLSECURITY/ATL::CDacl::CDacl
- ATLSECURITY/ATL::CDacl::AddAllowedAce
- ATLSECURITY/ATL::CDacl::AddDeniedAce
- ATLSECURITY/ATL::CDacl::GetAceCount
- ATLSECURITY/ATL::CDacl::RemoveAce
- ATLSECURITY/ATL::CDacl::RemoveAllAces
dev_langs: C++
helpviewer_keywords: CDacl class
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f45a4fc1d69cf0caefb08a7a408ecc836d092851
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdacl-class"></a>CDacl sınıfı
DACL (isteğe bağlı erişim denetim listesi) yapısı için bir sarmalayıcı sınıftır.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CDacl : public CAcl
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDacl::CDacl](#cdacl)|Oluşturucu.|  
|[CDacl:: ~ CDacl](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDacl::AddAllowedAce](#addallowedace)|İzin verilen ACE (erişim denetim girdisi) ekler `CDacl` nesnesi.|  
|[CDacl::AddDeniedAce](#adddeniedace)|Reddedilen bir AS ekler `CDacl` nesnesi.|  
|[CDacl::GetAceCount](#getacecount)|ACE'ler (erişim denetimi girdileri) sayısını döndürür `CDacl` nesnesi.|  
|[CDacl::RemoveAce](#removeace)|Belirli bir ACE (erişim denetim girdisi) kaldırır `CDacl` nesnesi.|  
|[CDacl::RemoveAllAces](#removeallaces)|Tüm bulunan ACE'ler kaldırır `CDacl` nesnesi.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDacl::operator =](#operator_eq)|Atama işleci.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir nesnenin güvenlik tanımlayıcısı DACL içerebilir. DACL kullanıcıları ve grupları nesne kimlerin erişebileceğini tanımlayan sıfır veya daha fazla ACE (erişim denetimi girdileri) içerir. DACL boşsa (diğer bir deyişle, sıfır ACE'ler içerdiği), erişim örtük olarak reddedildi için erişim yok açıkça verilir. Ancak, bir nesnenin güvenlik tanımlayıcısı DACL yoksa korumasız bir nesnedir ve herkesin tam erişimi vardır.  
  
 Bir nesnenin DACL almak için nesnenin sahibi olmanız veya nesne READ_CONTROL erişiminizin olması gerekir. Bir nesnenin DACL değiştirmek için nesne WRITE_DAC erişimi olması gerekir.  
  
 Oluşturmak, eklemek, kaldırmak ve gelen ACE'ler silmek için sağlanan sınıfı yöntemleri kullanmak `CDacl` nesnesi. Ayrıca bkz. [AtlGetDacl](security-global-functions.md#atlgetdacl) ve [AtlSetDacl](security-global-functions.md#atlsetdacl).  
  
 Erişim denetimi modeli Windows giriş için bkz: [erişim denetimi](http://msdn.microsoft.com/library/windows/desktop/aa374860) Windows SDK'sındaki.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CDacl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsecurity.h  
  
##  <a name="addallowedace"></a>CDacl::AddAllowedAce  
 İzin verilen ACE (erişim denetim girdisi) ekler `CDacl` nesnesi.  
  
```
bool AddAllowedAce(  
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddAllowedAce(  
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rSid`  
 A [CSID](../../atl/reference/csid-class.md) nesnesi.  
  
 `AccessMask`  
 İzin verilmesi için erişim haklarını maskesini belirtir için belirtilen `CSid` nesnesi.  
  
 `AceFlags`  
 ACE devralmayı denetlemek bit bayrakları kümesi.  
  
 `pObjectType`  
 Nesne türü.  
  
 `pInheritedObjectType`  
 Devralınan nesne türü.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** ACE eklenirse `CDacl` nesnesi **false** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 A `CDacl` nesnesi kullanıcılar ve nesne erişebilen grupları tanımlar sıfır veya daha fazla ACE (erişim denetimi girdileri) içerir. Bu yöntem erişimine izin veren bir ACE ekler `CDacl` nesnesi.  
  
> [!NOTE]
>  İkinci biçiminde `AddAllowedAce` yalnızca Windows 2000 kullanılabilir ve üzerinde desteklenir.  
  
 Bkz: [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) içinde ayarlanan çeşitli bayrakları açıklaması `AceFlags` parametresi.  
  
##  <a name="adddeniedace"></a>CDacl::AddDeniedAce  
 Reddedilen ACE (erişim denetim girdisi) ekler `CDacl` nesnesi.  
  
```
bool AddDeniedAce(  
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rSid`  
 A `CSid` nesnesi.  
  
 `AccessMask`  
 Erişim hakları reddedilmesi maskesini belirtir için belirtilen `CSid` nesnesi.  
  
 `AceFlags`  
 ACE devralmayı denetlemek bit bayrakları kümesi. Varsayılan olarak 0 yönteminin ilk biçiminde.  
  
 `pObjectType`  
 Nesne türü.  
  
 `pInheritedObjectType`  
 Devralınan nesne türü.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** ACE eklenirse `CDacl` nesnesi **false** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 A `CDacl` nesnesi kullanıcılar ve nesne erişebilen grupları tanımlar sıfır veya daha fazla ACE (erişim denetimi girdileri) içerir. Bu yöntem için erişimini engellediği ACE ekler `CDacl` nesnesi.  
  
> [!NOTE]
>  İkinci biçiminde `AddDeniedAce` yalnızca Windows 2000 kullanılabilir ve üzerinde desteklenir.  
  
 Bkz: [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) içinde ayarlanan çeşitli bayrakları açıklaması `AceFlags` parametresi.  
  
##  <a name="cdacl"></a>CDacl::CDacl  
 Oluşturucu.  
  
```
CDacl (const ACL& rhs) throw(...);  
CDacl () throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `rhs`  
 Var olan **ACL** (erişim denetim listesi) yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 `CDacl` Nesne isteğe bağlı olarak var olan kullanılarak oluşturulabilir **ACL** yapısı. DACL yalnızca (isteğe bağlı erişim denetim listesi) dikkate almak önemlidir ve SACL yok (sistem erişim denetim listesi), bu parametre olarak geçirilen. Hata ayıklama derlemelerinde SACL geçirme ASSERT neden olur. Yayın derlemeleri SACL geçirme (erişim denetimi girdileri) ACE'ler yok sayılacak ACL'de neden olur ve herhangi bir hata meydana gelir.  
  
##  <a name="dtor"></a>CDacl:: ~ CDacl  
 Yok Edicisi.  
  
```
~CDacl () throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yıkıcı kullanarak tüm ACE'ler (erişim denetimi girdileri) dahil olmak üzere nesne tarafından alınan tüm kaynakları serbest bırakır [CDacl::RemoveAllAces](#removeallaces).  
  
##  <a name="getacecount"></a>CDacl::GetAceCount  
 ACE'ler (erişim denetimi girdileri) sayısını döndürür `CDacl` nesnesi.  
  
```
UINT GetAceCount() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 ACE'ler içinde yer alan sayısını döndürür `CDacl` nesnesi.  
  
##  <a name="operator_eq"></a>CDacl::operator =  
 Atama işleci.  
  
```
CDacl& operator= (const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rhs`  
 Var olan nesneye atamak için ACL (erişim denetim listesi).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş bir başvuru döndürür `CDacl` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 (İsteğe bağlı erişim denetim listesi) DACL yalnızca bu işleve geçirmek emin olun. SACL (sistem erişim denetim listesi) geçirme için bu işlevi ASSERT hata ayıklama derlemelerinde neden olur, ancak hiçbir hata yayın derlemelerde neden olur.  
  
##  <a name="removeace"></a>CDacl::RemoveAce  
 Belirli bir ACE (erişim denetim girdisi) kaldırır `CDacl` nesnesi.  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Kaldırmak için ACE giriş dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem türetilir [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).  
  
##  <a name="removeallaces"></a>CDacl::RemoveAllAces  
 Tüm bulunan ACE (erişim denetimi girdileri) kaldırır `CDacl` nesnesi.  
  
```
void RemoveAllAces() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kaldırır her **ACE** (erişim denetim girdisi) yapısı (varsa) içinde `CDacl` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Güvenliği örneği](../../visual-cpp-samples.md)   
 [CAcl sınıfı](../../atl/reference/cacl-class.md)   
 [ACL](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [ACE'ler](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [Güvenlik genel işlevler](../../atl/reference/security-global-functions.md)
