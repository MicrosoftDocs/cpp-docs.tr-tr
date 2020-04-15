---
title: CAutoRevertImpersonation Sınıfı
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
ms.openlocfilehash: 813b6f0dd33bdfa85476b816086217a7892f4476
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318786"
---
# <a name="cautorevertimpersonation-class"></a>CAutoRevertImpersonation Sınıfı

Bu sınıf, [CAccessToken](../../atl/reference/caccesstoken-class.md) nesnelerini kapsam dışına çıktığında taklit etmeyen bir duruma geri döner.

## <a name="syntax"></a>Sözdizimi

```
class CAutoRevertImpersonation
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAutoRevertTaklit::CAutoRevertTaklit](#cautorevertimpersonation)|Nesne `CAutoRevertImpersonation` yi inşa eder|
|[CAutoRevertTaklit::~CAutoRevertTaklit](#dtor)|Nesneyi yok eder ve erişim token kimliğe bürünme geri.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAutoRevertTaklit::Ekle](#attach)|Erişim belirtecinin kimliğe bürünme yeniden sürümünü otomatikleştirir.|
|[CAutoRevertTaklit::Detach](#detach)|Otomatik kimliğe bürünme yeniden sürümünü iptal eder.|
|[CAutoRevertImpersonation::GetAccessToken](#getaccesstoken)|Bu nesneyle ilişkili erişim belirteç akımını alır.|

## <a name="remarks"></a>Açıklamalar

[Erişim belirteci,](/windows/win32/SecAuthZ/access-tokens) bir işlemin veya iş parçacığının güvenlik bağlamını açıklayan ve windows nt veya Windows 2000 sistemine oturum açmış her kullanıcıya ayrılan bir nesnedir. Bu erişim belirteçleri `CAccessToken` sınıfla birlikte temsil edilebilir.

Bazen erişim belirteçleri taklit etmek gereklidir. Bu sınıf kolaylık sağlamak amacıyla sağlanır, ancak erişim belirteçleri kimliğe bürünme gerçekleştirmez; yalnızca kimliğim taklidi olmayan bir duruma otomatik reversion gerçekleştirir. Bunun nedeni, belirteç erişim kimliğe bürünme birkaç farklı şekilde gerçekleştirilebilir olmasıdır.

Windows'daki erişim denetimi modeline giriş için Windows SDK'daki [Access Denetimi'ne](/windows/win32/SecAuthZ/access-control) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsecurity.h

## <a name="cautorevertimpersonationattach"></a><a name="attach"></a>CAutoRevertTaklit::Ekle

Erişim belirtecinin kimliğe bürünme yeniden sürümünü otomatikleştirir.

```
void Attach(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>Parametreler

*pAT*<br/>
[CAccessToken](../../atl/reference/caccesstoken-class.md) nesnesinin adresi otomatik olarak döndürülecek

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca [CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) nesnesi NULL `CAccessToken` işaretçisi ile oluşturulduğunda veya [Ayırma](#detach) daha önce çağrıldıysa kullanılmalıdır. Basit durumlarda, bu yöntemi kullanmak gerekli değildir.

## <a name="cautorevertimpersonationcautorevertimpersonation"></a><a name="cautorevertimpersonation"></a>CAutoRevertTaklit::CAutoRevertTaklit

Bir `CAutoRevertImpersonation` nesne inşa eder.

```
CAutoRevertImpersonation(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>Parametreler

*pAT*<br/>
[CAccessToken](../../atl/reference/caccesstoken-class.md) nesnesinin adresi otomatik olarak döndürülecek.

### <a name="remarks"></a>Açıklamalar

Erişim belirteci gerçek kimliğe bürünme ayrı ve tercihen bir `CAutoRevertImpersonation` nesnenin oluşturulmasından önce gerçekleştirilmelidir. `CAutoRevertImpersonation` Nesne kapsam dışına çıktığında bu kimliğe bürünme otomatik olarak geri döndürülecektir.

## <a name="cautorevertimpersonationcautorevertimpersonation"></a><a name="dtor"></a>CAutoRevertTaklit::~CAutoRevertTaklit

Nesneyi yok eder ve erişim token kimliğe bürünme geri.

```
~CAutoRevertImpersonation() throw();
```

### <a name="remarks"></a>Açıklamalar

İnşaatta veya [Ekle](#attach) yöntemi yle sağlanan [CAccessToken](../../atl/reference/caccesstoken-class.md) nesnesi için şu anda geçerli olan herhangi bir kimliğe bürünme geri döner. Hayır `CAccessToken` ilişkili ise, yıkıcı hiçbir etkisi yoktur.

## <a name="cautorevertimpersonationdetach"></a><a name="detach"></a>CAutoRevertTaklit::Detach

Otomatik kimliğe bürünme yeniden sürümünü iptal eder.

```
const CAccessToken* Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Daha önce ilişkili [CAccessToken](../../atl/reference/caccesstoken-class.md)adresi , veya NULL eğer hiçbir ilişkilendirme var.

### <a name="remarks"></a>Açıklamalar

**Detach'ı** çağırmak, nesnenin `CAutoRevertImpersonation` bu nesneyle ilişkili [CAccessToken](../../atl/reference/caccesstoken-class.md) nesnesi için şu anda geçerli olan herhangi bir kimliğe bürünme sini geri almamasını engeller. `CAutoRevertImpersonation`daha sonra hiçbir etkisi olmadan yok edilebilir veya `CAccessToken` [ekle](#attach)kullanarak aynı veya başka bir nesne ile yeniden ilişkilendirilebilir.

## <a name="cautorevertimpersonationgetaccesstoken"></a><a name="getaccesstoken"></a>CAutoRevertImpersonation::GetAccessToken

Bu nesneyle ilişkili erişim belirteç akımını alır.

```
const CAccessToken* GetAccessToken() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Daha önce ilişkili [CAccessToken](../../atl/reference/caccesstoken-class.md)adresi , veya NULL eğer hiçbir ilişkilendirme var.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CAccessToken` nesnenin bir kimliğe bürünme reversion içeren amaçlar için çağrılırsa, Bunun yerine [Detach](#detach) yöntemi kullanılmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[ATLSecurity Örneği](../../overview/visual-cpp-samples.md)<br/>
[Erişim Belirteçleri](/windows/win32/SecAuthZ/access-tokens)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
