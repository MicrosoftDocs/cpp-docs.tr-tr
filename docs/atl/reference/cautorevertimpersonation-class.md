---
title: CAutoRevertImpersonation sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::Attach
- ATLSECURITY/ATL::CAutoRevertImpersonation::Detach
- ATLSECURITY/ATL::CAutoRevertImpersonation::GetAccessToken
dev_langs:
- C++
helpviewer_keywords:
- CAutoRevertImpersonation class
ms.assetid: 43732849-1940-4bd4-9d52-7a5698bb8838
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 942c446fc64bb7e4210bc82e21fc2511ae01503a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="cautorevertimpersonation-class"></a>CAutoRevertImpersonation sınıfı
Bu sınıf döner [CAccessToken](../../atl/reference/caccesstoken-class.md) kapsam dışına çıktığında nonimpersonating bir duruma nesneleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CAutoRevertImpersonation
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAutoRevertImpersonation::CAutoRevertImpersonation](#cautorevertimpersonation)|Oluşturan bir `CAutoRevertImpersonation` nesnesi|  
|[CAutoRevertImpersonation:: ~ CAutoRevertImpersonation](#dtor)|Nesne yok eder ve erişim belirteci kimliğe bürünme döner.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAutoRevertImpersonation::Attach](#attach)|Bir erişim belirteci, kimliğe bürünme geri al otomatikleştirir.|  
|[CAutoRevertImpersonation::Detach](#detach)|Otomatik kimliğe bürünme geri al iptal eder.|  
|[CAutoRevertImpersonation::GetAccessToken](#getaccesstoken)|Bu nesneyle ilişkili erişim belirteci geçerli alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir [erişim belirteci](http://msdn.microsoft.com/library/windows/desktop/aa374909) bir işlem veya iş parçacığı güvenlik bağlamında açıklayan ve Windows NT veya Windows 2000 sisteminde oturum açmış her kullanıcı için ayrılan bir nesnedir. Bu erişim belirteçleri ile temsil edilebilir `CAccessToken` sınıfı.  
  
 Bazen, erişim belirteçlerinin kimliğine bürünmek gereklidir. Bu sınıf kolaylık sağlanır, ancak kimliğine bürünme erişim belirteci gerçekleştirmez; yalnızca Otomatik Geri Al nonimpersonated durumuna da gerçekleştirir. Belirteç erişimi kimliğe bürünme birçok farklı yöntemle gerçekleştirilebilir olmasıdır.  
  
 Erişim denetimi modeli Windows giriş için bkz: [erişim denetimi](http://msdn.microsoft.com/library/windows/desktop/aa374860) Windows SDK'sındaki.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsecurity.h  
  
##  <a name="attach"></a>  CAutoRevertImpersonation::Attach  
 Bir erişim belirteci, kimliğe bürünme geri al otomatikleştirir.  
  
```
void Attach(const CAccessToken* pAT) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pAT`  
 Adresini [CAccessToken](../../atl/reference/caccesstoken-class.md) otomatik olarak döndürülmesi için nesnesi  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem yalnızca varsa kullanılmalıdır [CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) nesnesi, NULL ile oluşturulmuş `CAccessToken` işaretçisi veya [ayırma](#detach) önceden çağrıldı. Basit durumlar için bu yöntemi kullanmak gerekli değildir.  
  
##  <a name="cautorevertimpersonation"></a>  CAutoRevertImpersonation::CAutoRevertImpersonation  
 Oluşturan bir `CAutoRevertImpersonation` nesnesi.  
  
```
CAutoRevertImpersonation(const CAccessToken* pAT) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pAT`  
 Adresini [CAccessToken](../../atl/reference/caccesstoken-class.md) otomatik olarak döndürülmesi için nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Erişim belirteci gerçek kimliğine bürünme ayrı olarak gelen ve tercihen oluşturulmasını önce gerçekleştirilmesi bir `CAutoRevertImpersonation` nesnesi. Bu kimliğe bürünme otomatik olarak zaman geri alınacak `CAutoRevertImpersonation` nesne kapsam dışında gider.  
  
##  <a name="dtor"></a>  CAutoRevertImpersonation:: ~ CAutoRevertImpersonation  
 Nesne yok eder ve erişim belirteci kimliğe bürünme döner.  
  
```
~CAutoRevertImpersonation() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm kimliğe bürünme şu anda yürürlükte döner [CAccessToken](../../atl/reference/caccesstoken-class.md) yapım veya aracılığıyla sağlanan nesne [Attach](#attach) yöntemi. Öyle değilse `CAccessToken` olan ilişkili yıkıcı hiçbir etkisi olmaz.  
  
##  <a name="detach"></a>  CAutoRevertImpersonation::Detach  
 Otomatik kimliğe bürünme geri al iptal eder.  
  
```
const CAccessToken* Detach() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha önce ilişkili adresini [CAccessToken](../../atl/reference/caccesstoken-class.md), veya hiçbir ilişkisi varsa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırma **ayırma** engelleyen `CAutoRevertImpersonation` herhangi kimliğe bürünme şu anda yürürlükte dönülüyor nesnesinin [CAccessToken](../../atl/reference/caccesstoken-class.md) Bu nesneyle ilişkili nesne. `CAutoRevertImpersonation` sonra ile herhangi bir etkisi yok veya aynı veya başka bir yeniden ilişkilendirilmedikçe `CAccessToken` kullanarak nesne [Attach](#attach).  
  
##  <a name="getaccesstoken"></a>  CAutoRevertImpersonation::GetAccessToken  
 Bu nesneyle ilişkili erişim belirteci geçerli alır.  
  
```
const CAccessToken* GetAccessToken() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha önce ilişkili adresini [CAccessToken](../../atl/reference/caccesstoken-class.md), veya hiçbir ilişkisi varsa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem bir kimliğe bürünme geri al eklemek amacıyla çağrılırsa `CAccessToken` nesnesi [ayırma](#detach) yöntemi bunun yerine kullanılmalıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATLSecurity örnek](../../visual-cpp-samples.md)   
 [Erişim belirteçleri](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
