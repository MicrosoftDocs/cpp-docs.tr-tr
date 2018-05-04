---
title: CComSafeDeleteCriticalSection sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Init
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Lock
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Term
- ATLCORE/ATL::m_bInitialized
dev_langs:
- C++
helpviewer_keywords:
- CComSafeDeleteCriticalSection class
ms.assetid: 4d2932c4-ba8f-48ec-8664-1db8bed01314
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cff637f9e307f2714cd351f3c6bcaf1e4b78342e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ccomsafedeletecriticalsection-class"></a>CComSafeDeleteCriticalSection sınıfı
Bu sınıf, alma ve kritik bölüm nesnenin sahipliğini serbest bırakma için yöntemleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CComSafeDeleteCriticalSection : public CComCriticalSection
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection](#ccomsafedeletecriticalsection)|Oluşturucu.|  
|[CComSafeDeleteCriticalSection:: ~ CComSafeDeleteCriticalSection](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComSafeDeleteCriticalSection::Init](#init)|Oluşturur ve kritik bölüm nesnesini başlatır.|  
|[CComSafeDeleteCriticalSection::Lock](#lock)|Kritik bölüm nesnenin sahipliğini alır.|  
|[CComSafeDeleteCriticalSection::Term](#term)|Kritik bölüm nesnesi tarafından kullanılan sistem kaynaklarını serbest bırakır.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|[m_bInitialized](#m_binitialized)|Bayrakları olup olmadığını iç **CRITICAL_SECTION** nesnesi başlatılmadı.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComSafeDeleteCriticalSection` sınıfından türetilen [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md). Ancak, `CComSafeDeleteCriticalSection` üzerinden ek güvenlik mekanizmaları sağlar [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).  
  
 Bir örneği olduğunda `CComSafeDeleteCriticalSection` kapsamının dışına gider ya da açıkça hala geçerli ise bellekten silinmiş, kritik bölüm nesnesini otomatik olarak temizlenecek. Ayrıca, [CComSafeDeleteCriticalSection::Term](#term) yöntemi çıkmak düzgün biçimde kritik bölüm nesnesini henüz ayrılmadı veya bellekten zaten yayımladı.  
  
 Bkz: [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) kritik bölüm yardımcı sınıfları hakkında daha fazla bilgi için.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 `CComSafeDeleteCriticalSection`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcore.h  
  
##  <a name="ccomsafedeletecriticalsection"></a>  CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection  
 Oluşturucu.  
  
```
CComSafeDeleteCriticalSection();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlar [m_bInitialized](#m_binitialized) veri üyesini **false**.  
  
##  <a name="dtor"></a>  CComSafeDeleteCriticalSection:: ~ CComSafeDeleteCriticalSection  
 Yok Edicisi.  
  
```
~CComSafeDeleteCriticalSection() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 İç serbest **CRITICAL_SECTION** bellekten nesne [m_bInitialized](#m_binitialized) veri üyesi ayarlanmış **doğru**.  
  
##  <a name="init"></a>  CComSafeDeleteCriticalSection::Init  
 Temel sınıf uygulamasını çağıran [Init](/visualstudio/debugger/init) ve ayarlar [m_bInitialized](#m_binitialized) için **true** başarılı olursa.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sonucunu döndürür [CComCriticalSection::Init](../../atl/reference/ccomcriticalsection-class.md#init).  
  
##  <a name="lock"></a>  CComSafeDeleteCriticalSection::Lock  
Temel sınıf uygulamasını çağıran [kilit](ccomcriticalsection-class.md#lock).  

  
```
HRESULT Lock();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sonucunu döndürür [CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock).  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem varsayar [m_bInitialized](#m_binitialized) veri üyesi ayarlanmış **true** girişte. Bu condidtion karşılanmazsa onayı ifade hata ayıklama derlemelerinde oluşturulur.  
  
 İşlevi davranışı hakkında daha fazla bilgi için bkz [CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock).  
  
##  <a name="m_binitialized"></a>  CComSafeDeleteCriticalSection::m_bInitialized  
 Bayrakları olup olmadığını iç **CRITICAL_SECTION** nesnesi başlatılmadı.  
  
```
bool m_bInitialized;
```  
  
### <a name="remarks"></a>Açıklamalar  
 **M_bInitialized** temel geçerlilik izlemek için kullanılan veri üyesi **CRITICAL_SECTION** ilişkili nesne [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) sınıfı. Arka plandaki **CRITICAL_SECTION** nesnesi değil deneneceğini Bu bayrak ayarlanmazsa, bellekten yayımlanacak **doğru**.  
  
##  <a name="term"></a>  CComSafeDeleteCriticalSection::Term  
 Temel sınıf uygulamasını çağıran [CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term) , iç **CRITICAL_SECTION** nesne geçerlidir.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sonucunu döndürür [CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term), veya **S_OK** varsa [m_bInitialized](#m_binitialized) ayarlandı **false** girişte.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem olsa bile iç çağrılması güvenlidir **CRITICAL_SECTION** nesnesi geçerli değil. Bu sınıf yıkıcı varsa bu yöntemi çağırır [m_bInitialized](#m_binitialized) veri üyesi ayarlanmış **doğru**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComCriticalSection sınıfı](../../atl/reference/ccomcriticalsection-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
