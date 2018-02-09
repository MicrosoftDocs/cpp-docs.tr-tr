---
title: "CSacl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSacl
- ATLSECURITY/ATL::CSacl
- ATLSECURITY/ATL::CSacl::CSacl
- ATLSECURITY/ATL::CSacl::AddAuditAce
- ATLSECURITY/ATL::CSacl::GetAceCount
- ATLSECURITY/ATL::CSacl::RemoveAce
- ATLSECURITY/ATL::CSacl::RemoveAllAces
dev_langs:
- C++
helpviewer_keywords:
- CSacl class
ms.assetid: 8624889b-aebc-4183-9d29-a20f07837f05
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f4308211dd22c39311b4d767c4c4487d9bf23971
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="csacl-class"></a>CSacl sınıfı
SACL (sistem erişim denetim listesi) yapısı için bir sarmalayıcı sınıftır.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CSacl : public CAcl
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSacl::CSacl](#csacl)|Oluşturucu.|  
|[CSacl::~CSacl](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSacl::AddAuditAce](#addauditace)|Denetim erişim denetim girdisi (ACE) ekler `CSacl` nesnesi.|  
|[CSacl::GetAceCount](#getacecount)|Erişim denetimi girişlerinin (ACE'ler) sayısını döndürür `CSacl` nesnesi.|  
|[CSacl::RemoveAce](#removeace)|Belirli bir ACE (erişim denetim girdisi) kaldırır **CSacl** nesnesi.|  
|[CSacl::RemoveAllAces](#removeallaces)|Tüm bulunan ACE'ler kaldırır `CSacl` nesnesi.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSacl::operator =](#operator_eq)|Atama işleci.|  
  
## <a name="remarks"></a>Açıklamalar  
 SACL denetim kayıtlarının bir etki alanı denetleyicisi güvenlik olay günlüğünde oluşturmak erişim denemesi türlerini belirtmek erişim denetimi girişlerinin (ACE'ler) içerir. SACL günlük girişlerini erişim denemesi oluştuğu yalnızca etki alanı denetleyicisinde, nesnenin bir kopyasını içeren değil her etki alanı denetleyicisinde oluşturur unutmayın.  
  
 Ayarlayın veya bir nesnenin güvenlik tanımlayıcısı'nda SACL almak için istekte bulunan iş parçacığının erişim belirteci SE_SECURITY_NAME ayrıcalık etkinleştirilmesi gerekir. Yöneticiler grubuna varsayılan olarak verilen bu ayrıcalığı ve diğer kullanıcılar veya gruplar için verilebilir. Ayrıcalığına sahip verilen değil, gerekli olan: Ayrıcalık tarafından tanımlanan işlemi gerçekleştirilmeden önce ayrıcalık güvenlik erişim belirtecinde etkili olması için etkinleştirilmesi gerekir. Model yalnızca belirli sistem işlemleri için etkin ve artık gerekmediğinde sonra devre dışı ayrıcalıklarına sağlar. Bkz: [AtlGetSacl](security-global-functions.md#atlgetsacl) ve [AtlSetSacl](security-global-functions.md#atlsetsacl) SE_SECURITY_NAME etkinleştirme örnekler.  
  
 Ekle, Kaldır, oluşturun ve gelen ACE'ler silme sağlanan sınıfı yöntemleri kullanmak **SACL** nesnesi. Ayrıca bkz. [AtlGetSacl](security-global-functions.md#atlgetsacl) ve [AtlSetSacl](security-global-functions.md#atlsetsacl).  
  
 Erişim denetimi modeli Windows giriş için bkz: [erişim denetimi](http://msdn.microsoft.com/library/windows/desktop/aa374860) Windows SDK'sındaki.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CSacl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsecurity.h  
  
##  <a name="addauditace"></a>  CSacl::AddAuditAce  
 Denetim erişim denetim girdisi (ACE) ekler `CSacl` nesnesi.  
  
```
bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags = 0) throw(...);

bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rSid`  
 [CSID](../../atl/reference/csid-class.md) nesnesi.  
  
 `AccessMask`  
 Denetlenecek erişim hakları maskesini belirtir için belirtilen `CSid` nesnesi.  
  
 `bSuccess`  
 İzin verilen erişim denemesi denetlenecek olup olmadığını belirtir. Bu bayrak etkinleştir denetim true ayarlayın; Aksi takdirde false olarak ayarlayın.  
  
 *bFailure*  
 Reddedilen erişim denemesi denetlenecek olup olmadığını belirtir. Bu bayrak etkinleştir denetim true ayarlayın; Aksi takdirde false olarak ayarlayın.  
  
 `AceFlags`  
 ACE devralmayı denetlemek bit bayrakları kümesi.  
  
 `pObjectType`  
 Nesne türü.  
  
 `pInheritedObjectType`  
 Devralınan nesne türü.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** ACE eklenirse `CSacl` nesnesi **false** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 A `CSacl` nesnesini içeren erişim denetimi girişlerinin (ACE'ler) güvenlik olay günlüğünde denetim kaydı oluşturmak erişim denemesi türlerini belirtin. Bu yöntem bu tür bir AS ekler `CSacl` nesnesi.  
  
 Bkz: [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) içinde ayarlanan çeşitli bayrakları açıklaması `AceFlags` parametresi.  
  
##  <a name="csacl"></a>  CSacl::CSacl  
 Oluşturucu.  
  
```
CSacl() throw();
CSacl(const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rhs`  
 Var olan **ACL** (erişim denetim listesi) yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 `CSacl` Nesne isteğe bağlı olarak var olan kullanılarak oluşturulabilir **ACL** yapısı. Bu parametre bir sistem erişim denetimi listesi (SACL) ve bir isteğe bağlı erişim denetimi listesi (DACL) değil olduğundan emin olun. DACL sağlandıysa hata ayıklama derlemelerinde, bir onaylama meydana gelir. Yayın derlemeleri herhangi bir DACL girişlerinden göz ardı edilir.  
  
##  <a name="dtor"></a>  CSacl::~CSacl  
 Yok Edicisi.  
  
```
~CSacl() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yok Edicisi tüm erişim denetimi girişlerinin (ACE'ler) dahil olmak üzere nesne tarafından alınan tüm kaynakları serbest bırakır.  
  
##  <a name="getacecount"></a>  CSacl::GetAceCount  
 Erişim denetimi girişlerinin (ACE'ler) sayısını döndürür `CSacl` nesnesi.  
  
```
UINT GetAceCount() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 ACE'ler içinde yer alan sayısını döndürür `CSacl` nesnesi.  
  
##  <a name="operator_eq"></a>CSacl::operator =  
 Atama işleci.  
  
```
CSacl& operator=(const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rhs`  
 **ACL** (var olan nesneye atamak için erişim denetim listesi).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş bir başvuru döndürür `CSacl` nesnesi. Emin **ACL** parametredir gerçekte sistem erişim denetimi listesi (SACL) ve bir isteğe bağlı erişim denetimi listesi (DACL) değil. Hata ayıklama yapıları onayı ifade gerçekleşir ve yayın derlemeleri **ACL** parametresi yok sayılacak.  
  
##  <a name="removeace"></a>CSacl::RemoveAce  
 Belirli bir ACE (erişim denetim girdisi) kaldırır **CSacl** nesnesi.  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Kaldırmak için ACE giriş dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem türetilir [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).  
  
##  <a name="removeallaces"></a>CSacl::RemoveAllAces  
 Tüm bulunan erişim denetimi girişlerinin (ACE'ler) kaldırır `CSacl` nesnesi.  
  
```
void RemoveAllAces() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kaldırır her **ACE** (varsa) içinde yapısı `CSacl` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CAcl sınıfı](../../atl/reference/cacl-class.md)   
 [ACL](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [ACE'ler](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
