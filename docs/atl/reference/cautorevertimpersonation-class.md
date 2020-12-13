---
description: 'Daha fazla bilgi edinin: CAutoRevertImpersonation Class'
title: CAutoRevertImpersonation sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::Attach
- ATLSECURITY/ATL::CAutoRevertImpersonation::Detach
- ATLSECURITY/ATL::CAutoRevertImpersonation::GetAccessToken
helpviewer_keywords:
- CAutoRevertImpersonation class
ms.assetid: 43732849-1940-4bd4-9d52-7a5698bb8838
ms.openlocfilehash: 48009a4d146866d36eebc75ada8f9ae12058287a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147088"
---
# <a name="cautorevertimpersonation-class"></a>CAutoRevertImpersonation sınıfı

Bu sınıf, kapsam dışına geçtiğinde [CAccessToken](../../atl/reference/caccesstoken-class.md) nesnelerini taklit olmayan bir duruma döndürür.

## <a name="syntax"></a>Syntax

```
class CAutoRevertImpersonation
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAutoRevertImpersonation:: CAutoRevertImpersonation](#cautorevertimpersonation)|Bir `CAutoRevertImpersonation` nesne oluşturur|
|[CAutoRevertImpersonation:: ~ CAutoRevertImpersonation](#dtor)|Nesneyi yok eder ve erişim belirteci kimliğe bürünme işlemini geri alır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAutoRevertImpersonation:: Attach](#attach)|Bir erişim belirtecinin kimliğe bürünme yeniden sürümünü otomatikleştirir.|
|[CAutoRevertImpersonation::D etach](#detach)|Otomatik kimliğe bürünme yeniden sürümünü iptal eder.|
|[CAutoRevertImpersonation:: GetAccessToken](#getaccesstoken)|Bu nesneyle ilişkili geçerli erişim belirtecini alır.|

## <a name="remarks"></a>Açıklamalar

[Erişim belirteci](/windows/win32/SecAuthZ/access-tokens) bir işlemin veya iş parçacığının güvenlik bağlamını açıklayan ve BIR Windows NT veya Windows 2000 sisteminde oturum açan her kullanıcıya ayrılan bir nesnedir. Bu erişim belirteçleri sınıfıyla temsil edilebilir `CAccessToken` .

Bazen erişim belirteçlerinin taklit olması gerekir. Bu sınıf kolaylık olarak sunulmaktadır, ancak erişim belirteçleri kişiliğe bürünme işlemini gerçekleştirmez; yalnızca otomatik yeniden sürümü kimliğine bürünülmüş bir duruma getirir. Bunun nedeni, belirteç erişiminin kimliğe bürünme özelliğinin birçok farklı şekilde gerçekleştirilebilmesinden kaynaklanır.

Windows 'daki erişim denetim modeline giriş için Windows SDK [Access Control](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity. h

## <a name="cautorevertimpersonationattach"></a><a name="attach"></a> CAutoRevertImpersonation:: Attach

Bir erişim belirtecinin kimliğe bürünme yeniden sürümünü otomatikleştirir.

```cpp
void Attach(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>Parametreler

*Başak*<br/>
Otomatik olarak geri döndürülecek [CAccessToken](../../atl/reference/caccesstoken-class.md) nesnesinin adresi

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca, [CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) nesnesi null `CAccessToken` işaretçiyle oluşturulduysa veya [ayırma](#detach) daha önce çağrılırsa kullanılmalıdır. Basit durumlarda, bu yöntemin kullanılması gerekli değildir.

## <a name="cautorevertimpersonationcautorevertimpersonation"></a><a name="cautorevertimpersonation"></a> CAutoRevertImpersonation:: CAutoRevertImpersonation

Bir `CAutoRevertImpersonation` nesnesi oluşturur.

```
CAutoRevertImpersonation(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>Parametreler

*Başak*<br/>
Otomatik olarak geri döndürülecek [CAccessToken](../../atl/reference/caccesstoken-class.md) nesnesinin adresi.

### <a name="remarks"></a>Açıklamalar

Erişim belirtecinin gerçek kimliğe bürünme işleminden ayrı olarak ve tercihen bir nesne oluşturmadan önce gerçekleştirilmelidir `CAutoRevertImpersonation` . Nesne kapsam dışına geçtiğinde bu kimliğe bürünme otomatik olarak geri döndürülür `CAutoRevertImpersonation` .

## <a name="cautorevertimpersonationcautorevertimpersonation"></a><a name="dtor"></a> CAutoRevertImpersonation:: ~ CAutoRevertImpersonation

Nesneyi yok eder ve erişim belirteci kimliğe bürünme işlemini geri alır.

```
~CAutoRevertImpersonation() throw();
```

### <a name="remarks"></a>Açıklamalar

Oluşturma sırasında veya [Attach](#attach) yöntemi aracılığıyla belirtilen [CAccessToken](../../atl/reference/caccesstoken-class.md) nesnesi için geçerli olarak kimliğe bürünme işlemini geri döndürür. Hayır `CAccessToken` ilişkili değilse, yok edicinin hiçbir etkisi yoktur.

## <a name="cautorevertimpersonationdetach"></a><a name="detach"></a> CAutoRevertImpersonation::D etach

Otomatik kimliğe bürünme yeniden sürümünü iptal eder.

```
const CAccessToken* Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Daha önce ilişkili [CAccessToken](../../atl/reference/caccesstoken-class.md)adresi veya ILIŞKILENDIRME yoksa null.

### <a name="remarks"></a>Açıklamalar

**Ayırma** çağrısı, `CAutoRevertImpersonation` nesnenin bu nesneyle Ilişkili [CAccessToken](../../atl/reference/caccesstoken-class.md) nesnesi için şu anda etkin olan kimliğe bürünme işlemini geri almasını engeller. `CAutoRevertImpersonation`daha sonra, herhangi bir etkisi olmadan veya Iliştirme kullanılarak aynı ya da başka bir nesneyle yeniden ilişkilendirilmeden yok edilebilir `CAccessToken` . [](#attach)

## <a name="cautorevertimpersonationgetaccesstoken"></a><a name="getaccesstoken"></a> CAutoRevertImpersonation:: GetAccessToken

Bu nesneyle ilişkili geçerli erişim belirtecini alır.

```
const CAccessToken* GetAccessToken() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Daha önce ilişkili [CAccessToken](../../atl/reference/caccesstoken-class.md)adresi veya ILIŞKILENDIRME yoksa null.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, nesnenin kimliğe bürünme özelliğinin yeniden sürümünü içeren amaçlarla çağrılırsa `CAccessToken` , bunun yerine [Detach](#detach) yöntemi kullanılmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[ATLSecurity örneği](../../overview/visual-cpp-samples.md)<br/>
[Erişim belirteçleri](/windows/win32/SecAuthZ/access-tokens)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
