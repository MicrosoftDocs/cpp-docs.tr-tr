---
description: 'Daha fazla bilgi edinin: Csettingsstosorumclass'
title: Csettingsstosorumclass
ms.date: 11/04/2016
f1_keywords:
- CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::Create
- AFXSETTINGSSTORE/CSettingsStoreSP::SetRuntimeClass
helpviewer_keywords:
- CSettingsStoreSP [MFC], CSettingsStoreSP
- CSettingsStoreSP [MFC], Create
- CSettingsStoreSP [MFC], SetRuntimeClass
ms.assetid: bcd37f40-cfd4-4d17-a5ce-3bfabe995dcc
ms.openlocfilehash: 67e9f881fc43722ab568aa7f149fc7a2b44cc764
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264693"
---
# <a name="csettingsstoresp-class"></a>Csettingsstosorumclass

`CSettingsStoreSP`Sınıfı, [Csettingssbir sınıfının](../../mfc/reference/csettingsstore-class.md)örneklerini oluşturmak için kullanabileceğiniz bir yardımcı sınıftır.

## <a name="syntax"></a>Syntax

```
class CSettingsStoreSP
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Csettingsstosorum:: Csettingsstosorum](#csettingsstoresp)|Bir `CSettingsStoreSP` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Csettingsstosorum:: oluştur](#create)|Sınıfından türetilmiş bir sınıf örneği oluşturur `CSettingsStore` .|
|[Csettingsstosorum:: SetRuntimeClass](#setruntimeclass)|Çalışma zamanı sınıfını ayarlar. `Create`Yöntemi, hangi nesne sınıfının oluşturulacağını belirlemek için çalışma zamanı sınıfını kullanır.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|`m_dwUserData`|Nesnede depolanan özel kullanıcı verileri `CSettingsStoreSP` . Bu verileri nesnenin kurucusunda sağlarsınız `CSettingsStoreSP` .|
|`m_pRegistry`|`CSettingsStore` `Create` Yöntemin oluşturduğu türetilmiş nesne.|

## <a name="remarks"></a>Açıklamalar

`CSettingsStoreSP`Sınıfını, tüm MFC kayıt defteri işlemlerini BIR XML dosyası veya veritabanı gibi diğer konumlara yeniden yönlendirmek için kullanabilirsiniz. Bunu yapmak için şu adımları izleyin:

1. Bir sınıf (gibi) oluşturun `CMyStore` ve öğesinden türetebilirsiniz `CSettingsStore` .

1. Dinamik oluşturmayı etkinleştirmek için özel sınıfınıza [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate) ve [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate) makroları kullanın `CSettingsStore` .

1. Sanal işlevleri geçersiz kılın ve `Read` `Write` özel sınıfınıza ve işlevlerini uygulayın. İstediğiniz konuma verileri okumak ve yazmak için başka işlevler uygulayın.

1. Uygulamanızda, `CSettingsStoreSP::SetRuntimeClass` sınıfınızdan elde edilen [CRuntimeClass yapısına](../../mfc/reference/cruntimeclass-structure.md) yönelik bir işaretçi çağırın ve geçirin.

Framework genellikle kayıt defterine her eriştiğinizde, özel sınıfınızı dinamik olarak başlatır ve verileri okumak veya yazmak için kullanın.

`CSettingsStoreSP::SetRuntimeClass` genel bir statik değişken kullanır. Bu nedenle, aynı anda yalnızca bir özel depo kullanılabilir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxsettingssfer. h

## <a name="csettingsstorespcreate"></a><a name="create"></a> Csettingsstosorum:: oluştur

[Csettingssbir sınıfından](../../mfc/reference/csettingsstore-class.md)türetilmiş nesnenin yeni bir örneğini oluşturur.

```
CSettingsStore& CSettingsStoreSP Create(
    BOOL bAdmin,
    BOOL bReadOnly);
```

### <a name="parameters"></a>Parametreler

*bAdmin*<br/>
'ndaki Bir nesnenin yönetici modunda oluşturulup oluşturulmayacağını belirleyen bir Boolean parametresi `CSettingsStore` .

*bReadOnly*<br/>
'ndaki `CSettingsStore` Salt okuma erişimi için bir nesnenin oluşturulup oluşturulmayacağını belirleyen bir Boolean parametresi.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan nesneye bir başvuru `CSettingsStore` .

### <a name="remarks"></a>Açıklamalar

Hangi tür nesnenin oluşturulacağını belirlemek için [Csettingsstosorum:: SetRuntimeClass](#setruntimeclass) yöntemini kullanabilirsiniz `CSettingsStoreSP::Create` . Varsayılan olarak, bu yöntem bir `CSettingsStore` nesnesi oluşturur.

`CSettingsStore`Yönetici modunda bir nesne oluşturursanız, tüm kayıt defteri erişimi için varsayılan konum HKEY_LOCAL_MACHINE olur. Aksi takdirde, tüm kayıt defteri erişimi için varsayılan konum HKEY_CURRENT_USER.

*BADMIN* true ise, uygulamanın yönetim haklarına sahip olması gerekir. Aksi takdirde, kayıt defterine erişmeyi denediğinde başarısız olur.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının yönteminin nasıl kullanılacağını gösterir `Create` `CSettingsStoreSP` .

[!code-cpp[NVC_MFC_RibbonApp#33](../../mfc/reference/codesnippet/cpp/csettingsstoresp-class_1.cpp)]

## <a name="csettingsstorespcsettingsstoresp"></a><a name="csettingsstoresp"></a> Csettingsstosorum:: Csettingsstosorum

[Csettingsstosorumclass](../../mfc/reference/csettingsstoresp-class.md) nesnesi oluşturur.

```
CSettingsStoreSP::CSettingsStoreSP(DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parametreler

*dwUserData*<br/>
'ndaki Nesnenin depoladığı Kullanıcı tanımlı veriler `CSettingsStoreSP` .

### <a name="remarks"></a>Açıklamalar

`CSettingsStoreSP`Nesne, verileri *dwUserData* 'den korumalı üye değişkeninde depolar `m_dwUserData` .

## <a name="csettingsstorespsetruntimeclass"></a><a name="setruntimeclass"></a> Csettingsstosorum:: SetRuntimeClass

Çalışma zamanı sınıfını ayarlar. [Csettingsstosorum:: Create](#create) yöntemi, oluşturulacak nesne türünü belirlemek için çalışma zamanı sınıfını kullanır.

```
static BOOL __stdcall CSettingsStoreSP::SetRuntimeClass(CRuntimeClass* pRTI);
```

### <a name="parameters"></a>Parametreler

*pRTI*<br/>
'ndaki [Csettingsstüreme sınıfından](../../mfc/reference/csettingsstore-class.md)türetilmiş bir sınıf için çalışma zamanı sınıf bilgilerine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa doğru; *PRTI* tarafından tanımlanan sınıf öğesinden TÜRETILDIYSE false `CSettingsStore` .

### <a name="remarks"></a>Açıklamalar

Sınıfları türetmek için [Csettingsstosorumclass](../../mfc/reference/csettingsstoresp-class.md) ' i kullanabilirsiniz `CSettingsStore` . `SetRuntimeClass`Sınıfından türetilmiş özel bir sınıfın nesnelerini oluşturmak istiyorsanız yöntemini kullanın `CSettingsStore` .

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Csettingssstore sınıfı](../../mfc/reference/csettingsstore-class.md)
