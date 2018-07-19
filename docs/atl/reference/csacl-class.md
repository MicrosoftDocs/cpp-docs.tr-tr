---
title: CSacl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 65375b764c0d8d8673a59fcfb47b4eecaf730cb5
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879963"
---
# <a name="csacl-class"></a>CSacl sınıfı
(Sistem erişim denetim listesi) SACL yapısı için bir sarmalayıcı sınıftır.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CSacl : public CAcl
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSacl::CSacl](#csacl)|Oluşturucu.|  
|[CSacl::~CSacl](#dtor)|Yıkıcı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSacl::AddAuditAce](#addauditace)|Bir denetim erişim denetimi girişi (ACE) ekler `CSacl` nesne.|  
|[CSacl::GetAceCount](#getacecount)|Erişim denetimi girdileri (ACE) sayısını döndürür `CSacl` nesne.|  
|[CSacl::RemoveAce](#removeace)|Belirli bir ACE (erişim denetimi girişi) kaldırır `CSacl` nesne.|  
|[CSacl::RemoveAllAces](#removeallaces)|Tüm bulunan ACE kaldırır `CSacl` nesne.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSacl::operator =](#operator_eq)|Atama işleci.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir SACL denetim kayıtlarının bir etki alanı denetleyicisi güvenlik olay günlüğünde oluşturan erişim denemesi türlerini belirtmek erişim denetimi girdileri (ACE) içerir. Bir SACL günlük girişlerini erişim denemesi oluştuğu yalnızca etki alanı denetleyicisinde, nesnenin bir kopyasını içeren değil her etki alanı denetleyicisinde oluşturur unutmayın.  
  
 Ayarlamak veya bir nesnenin güvenlik tanımlayıcısındaki SACL almak için istekte bulunan iş parçacığının erişim belirtecinde SE_SECURITY_NAME ayrıcalık etkinleştirilmesi gerekir. Yöneticiler grubuna varsayılan olarak verilen bu ayrıcalığı ve diğer kullanıcılar veya gruplar verilebilir. Ayrıcalığına sahip verilen değil tüm gereklidir: Ayrıcalık tarafından tanımlanan işlemi gerçekleştirilmeden önce ayrıcalık güvenlik erişim belirtecinde etkili olması için etkinleştirilmesi gerekir. Yalnızca belirli sistem işlemleri için etkin ve sonra artık gerekli değilse devre dışı ayrıcalıkları modeli sağlar. Bkz: [AtlGetSacl](security-global-functions.md#atlgetsacl) ve [AtlSetSacl](security-global-functions.md#atlsetsacl) SE_SECURITY_NAME etkinleştirme örnekler.  
  
 Ekle, Kaldır, oluşturma ve ACE öğesinden silmek için sağlanan sınıf yöntemleriyle `SACL` nesne. Ayrıca bkz: [AtlGetSacl](security-global-functions.md#atlgetsacl) ve [AtlSetSacl](security-global-functions.md#atlsetsacl).  
  
 Windows, erişim denetimi modeli için bir giriş için bkz [erişim denetimi](http://msdn.microsoft.com/library/windows/desktop/aa374860) Windows SDK.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CSacl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsecurity.h  
  
##  <a name="addauditace"></a>  CSacl::AddAuditAce  
 Bir denetim erişim denetimi girişi (ACE) ekler `CSacl` nesne.  
  
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
 *rSid*  
 [CSID](../../atl/reference/csid-class.md) nesne.  
  
 *AccessMask*  
 Denetlenecek erişim hakları maskesi belirtir için belirtilen `CSid` nesne.  
  
 *bSuccess*  
 İzin verilen erişim denemesi denetlenmesi olup olmadığını belirtir. Bu bayrak denetimini etkinleştirmek için true olarak ayarlayın; Aksi takdirde false olarak ayarlayın.  
  
 *bFailure*  
 Engellenen erişim girişimlerini denetlenmesi olup olmadığını belirtir. Bu bayrak denetimini etkinleştirmek için true olarak ayarlayın; Aksi takdirde false olarak ayarlayın.  
  
 *AceFlags*  
 ACE devralma denetleyen bit bayrakları kümesini.  
  
 *pObjectType*  
 Nesne türü.  
  
 *pInheritedObjectType*  
 Devralınan bir nesne türü.  
  
### <a name="return-value"></a>Dönüş Değeri  
 ACE eklenirse TRUE döndürür `CSacl` yanlış hatasında nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 A `CSacl` nesne erişim denetimi girdileri (ACE) güvenlik olay günlüğünde denetim kayıtlarını oluşturan erişim denemesi türlerini belirtmek içerir. Bu yöntem bir tür as ekler `CSacl` nesne.  
  
 Bkz: [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) içinde ayarlanan çeşitli bayrakları açıklamasını *AceFlags* parametresi.  
  
##  <a name="csacl"></a>  CSacl::CSacl  
 Oluşturucu.  
  
```
CSacl() throw();
CSacl(const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 *Sol*  
 Mevcut bir `ACL` yapısı (erişim denetim listesi).  
  
### <a name="remarks"></a>Açıklamalar  
 `CSacl` Nesne isteğe bağlı olarak oluşturulabilir var olan bir `ACL` yapısı. Bu parametre bir sistem erişim denetimi listesini (SACL) ve bir isteğe bağlı erişim denetimi listesini (DACL) değil olduğundan emin olun. Hata ayıklama yapılarında DACL sağlanmazsa, bir onaylama işlemi meydana gelir. Sürüm yapılandırmasında herhangi bir DACL girişlerinden göz ardı edilir.  
  
##  <a name="dtor"></a>  CSacl::~CSacl  
 Yıkıcı.  
  
```
~CSacl() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yok edici tüm erişim denetimi girdileri (ACE) dahil olmak üzere nesne tarafından alınan tüm kaynakları serbest bırakır.  
  
##  <a name="getacecount"></a>  CSacl::GetAceCount  
 Erişim denetimi girdileri (ACE) sayısını döndürür `CSacl` nesne.  
  
```
UINT GetAceCount() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 ACE'ler yer alan sayısını döndürür `CSacl` nesne.  
  
##  <a name="operator_eq"></a>  CSacl::operator =  
 Atama işleci.  
  
```
CSacl& operator=(const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 *Sol*  
 `ACL` (Var olan nesneye atamak için erişim denetim listesi).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş bir başvuru döndürür `CSacl` nesne. Emin `ACL` parametredir gerçekten sistem erişim denetimi listesi (SACL) ve bir isteğe bağlı erişim denetimi listesini (DACL) değil. Hata ayıklama yapılarında onaylama gerçekleşir ve sürüm yapıları `ACL` parametre yoksayılacak.  
  
##  <a name="removeace"></a>  CSacl::RemoveAce  
 Belirli bir ACE (erişim denetimi girişi) kaldırır `CSacl` nesne.  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Kaldırmak için ACE giriş dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem türetilmiş [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).  
  
##  <a name="removeallaces"></a>  CSacl::RemoveAllAces  
 Tüm yer alan erişim denetimi girişlerinin (ACE'ler) kaldırır `CSacl` nesne.  
  
```
void RemoveAllAces() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kaldırır her `ACE` (varsa), yapı `CSacl` nesne.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CAcl sınıfı](../../atl/reference/cacl-class.md)   
 [ACL'ler](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [ACE](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)   
 [Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
