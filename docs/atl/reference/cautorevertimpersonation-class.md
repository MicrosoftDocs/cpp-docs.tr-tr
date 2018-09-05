---
title: Cautorevertımpersonation sınıfı | Microsoft Docs
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
ms.openlocfilehash: 99f0615dc37070311428ec12894bcaeea8febe8d
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43760623"
---
# <a name="cautorevertimpersonation-class"></a>Cautorevertımpersonation sınıfı

Bu sınıf döner [CAccessToken](../../atl/reference/caccesstoken-class.md) kapsam dışına çıktığında nonimpersonating durumuna nesneleri.

## <a name="syntax"></a>Sözdizimi

```
class CAutoRevertImpersonation
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAutoRevertImpersonation::CAutoRevertImpersonation](#cautorevertimpersonation)|Oluşturur bir `CAutoRevertImpersonation` nesnesi|
|[Cautorevertımpersonation:: ~ Cautorevertımpersonation](#dtor)|Nesnesini yok eder ve erişim belirteci kimliğe bürünme döner.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAutoRevertImpersonation::Attach](#attach)|Kimliğe bürünme geri al, bir erişim belirteci otomatikleştirir.|
|[CAutoRevertImpersonation::Detach](#detach)|Otomatik kimliğe bürünme geri al iptal eder.|
|[CAutoRevertImpersonation::GetAccessToken](#getaccesstoken)|Bu nesneyle ilişkili erişim belirteci geçerli alır.|

## <a name="remarks"></a>Açıklamalar

Bir [erişim belirteci](/windows/desktop/SecAuthZ/access-tokens) bir işlem veya iş parçacığı güvenlik bağlamı açıklayan ve Windows NT veya Windows 2000 sisteminde oturum açmış her kullanıcı için ayrılan bir nesnedir. Bu erişim belirteçleri ile gösterilebilir `CAccessToken` sınıfı.

Bazen, erişim belirteçlerinin kimliğine bürünmek gereklidir. Bu sınıf, kolaylık olarak sağlanır, ancak erişim belirteçlerinin kimliğine bürünme işlemi gerçekleştirmez. yalnızca Otomatik Geri Al nonimpersonated durumuna da gerçekleştirir. Belirteç erişimi kimliğe bürünme, birçok farklı yöntemle gerçekleştirilebilir olmasıdır.

Windows, erişim denetimi modeli için bir giriş için bkz [erişim denetimi](/windows/desktop/SecAuthZ/access-control) Windows SDK.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsecurity.h

##  <a name="attach"></a>  CAutoRevertImpersonation::Attach

Kimliğe bürünme geri al, bir erişim belirteci otomatikleştirir.

```
void Attach(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>Parametreler

*pAT*  
Adresini [CAccessToken](../../atl/reference/caccesstoken-class.md) otomatik olarak döndürülecek nesne

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca varsa kullanılmalıdır [Cautorevertımpersonation](../../atl/reference/cautorevertimpersonation-class.md) nesnesi, NULL ile oluşturulmuş `CAccessToken` işaretçisi veya [ayırma](#detach) daha önce çağrıldı. Basit durumlar için bu yöntemi kullanmak gerekli değildir.

##  <a name="cautorevertimpersonation"></a>  CAutoRevertImpersonation::CAutoRevertImpersonation

Oluşturur bir `CAutoRevertImpersonation` nesne.

```
CAutoRevertImpersonation(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>Parametreler

*pAT*  
Adresini [CAccessToken](../../atl/reference/caccesstoken-class.md) otomatik olarak döndürülecek nesne.

### <a name="remarks"></a>Açıklamalar

Erişim belirtecinin gerçek kimliğe bürünme ayrı olarak gelen ve tercihen oluşturulmasını önce gerçekleştirilmesi bir `CAutoRevertImpersonation` nesne. Bu kimliğe bürünme otomatik olarak bir zaman döndürülecek `CAutoRevertImpersonation` nesne kapsam dışına gider.

##  <a name="dtor"></a>  Cautorevertımpersonation:: ~ Cautorevertımpersonation

Nesnesini yok eder ve erişim belirteci kimliğe bürünme döner.

```
~CAutoRevertImpersonation() throw();
```

### <a name="remarks"></a>Açıklamalar

Tüm kimliğe bürünme şu anda yürürlükte döner [CAccessToken](../../atl/reference/caccesstoken-class.md) nesne oluşturma sırasında veya aracılığıyla sağlanan [iliştirme](#attach) yöntemi. Hayır ise `CAccessToken` olan ilişkili bir yıkıcı hiçbir etkisi olmaz.

##  <a name="detach"></a>  CAutoRevertImpersonation::Detach

Otomatik kimliğe bürünme geri al iptal eder.

```
const CAccessToken* Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Daha önce ilişkili adresini [CAccessToken](../../atl/reference/caccesstoken-class.md), veya hiçbir ilişki mevcut değilse NULL.

### <a name="remarks"></a>Açıklamalar

Çağırma **ayırma** engeller `CAutoRevertImpersonation` herhangi kimliğe bürünme şu anda yürürlükte dönüştürme nesnesinin [CAccessToken](../../atl/reference/caccesstoken-class.md) Bu nesneyle ilişkili nesne. `CAutoRevertImpersonation` sonra herhangi bir etkisi yok veya aynı veya başka bir yeniden ilişkilendirilebilir `CAccessToken` kullanarak nesne [iliştirme](#attach).

##  <a name="getaccesstoken"></a>  CAutoRevertImpersonation::GetAccessToken

Bu nesneyle ilişkili erişim belirteci geçerli alır.

```
const CAccessToken* GetAccessToken() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Daha önce ilişkili adresini [CAccessToken](../../atl/reference/caccesstoken-class.md), veya hiçbir ilişki mevcut değilse NULL.

### <a name="remarks"></a>Açıklamalar

Geri Al bir kimliğe bürünme eklemek amacıyla bu yöntemi çağrılırsa `CAccessToken` nesnesi [ayırma](#detach) yöntemi bunun yerine kullanılmalıdır.

## <a name="see-also"></a>Ayrıca Bkz.

[ATLSecurity örnek](../../visual-cpp-samples.md)   
[Erişim belirteçleri](/windows/desktop/SecAuthZ/access-tokens)   
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
