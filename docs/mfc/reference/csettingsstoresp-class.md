---
title: CSettingsStoreSP Sınıfı
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
ms.openlocfilehash: 9e22184a4081762a3d505645752e514315146981
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318448"
---
# <a name="csettingsstoresp-class"></a>CSettingsStoreSP Sınıfı

Sınıf, `CSettingsStoreSP` [CSettingsStore Sınıfı'nın](../../mfc/reference/csettingsstore-class.md)örneklerini oluşturmak için kullanabileceğiniz yardımcı sınıftır.

## <a name="syntax"></a>Sözdizimi

```
class CSettingsStoreSP
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSettingsStoreSP::CsettingsStoreSP](#csettingsstoresp)|Bir `CSettingsStoreSP` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSettingsStoreSP::Oluştur](#create)|Türetilen bir sınıfın örneğini `CSettingsStore`oluşturur.|
|[CSettingsStoreSP::SetRuntimeClass](#setruntimeclass)|Çalışma zamanı sınıfını ayarlar. Yöntem, `Create` hangi nesne sınıfının oluşturulacak larını belirlemek için çalışma zamanı sınıfını kullanır.|

### <a name="data-members"></a>Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|`m_dwUserData`|`CSettingsStoreSP` Nesnede depolanan özel kullanıcı verileri. Bu verileri `CSettingsStoreSP` nesnenin oluşturucusunda sağlıyorsunuz.|
|`m_pRegistry`|Yöntemin `CSettingsStore` `Create` oluşturduğu türetilmiş nesne.|

## <a name="remarks"></a>Açıklamalar

Sınıfı, `CSettingsStoreSP` tüm MFC kayıt defteri işlemlerini XML dosyası veya veritabanı gibi diğer konumlara yönlendirmek için kullanabilirsiniz. Bunu yapmak için şu adımları uygulayın:

1. Bir sınıf (gibi) `CMyStore`oluşturun ve `CSettingsStore`türetin.

1. Dinamik oluşturmayı etkinleştirmek için `CSettingsStore` özel sınıfınızla [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate) ve [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate) makroları kullanın.

1. Sanal işlevleri geçersiz kılın `Read` ve `Write` özel sınıfınızdaki işlevleri uygulayın. İstediğiniz konuma veri okumak ve yazmak için diğer işlevleri uygulayın.

1. Uygulamanızda, sınıfınızdan alınan `CSettingsStoreSP::SetRuntimeClass` [CRuntimeClass Yapısı'na](../../mfc/reference/cruntimeclass-structure.md) bir işaretçi çağırın ve geçirin.

Çerçeve genellikle kayıt defterine erişse, artık özel sınıfınızı dinamik olarak anında hale getirecek ve verileri okumak veya yazmak için kullanır.

`CSettingsStoreSP::SetRuntimeClass`global statik değişken kullanır. Bu nedenle, aynı anda yalnızca bir özel mağaza kullanılabilir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxsettingsstore.h

## <a name="csettingsstorespcreate"></a><a name="create"></a>CSettingsStoreSP::Oluştur

[CSettingsStore Sınıfından](../../mfc/reference/csettingsstore-class.md)türetilen bir nesnenin yeni bir örneğini oluşturur.

```
CSettingsStore& CSettingsStoreSP Create(
    BOOL bAdmin,
    BOOL bReadOnly);
```

### <a name="parameters"></a>Parametreler

*bYönetici*<br/>
[içinde] Bir nesnenin yönetici modunda oluşturulup oluşturulmadığını belirleyen boolean `CSettingsStore` parametresi.

*bReadOnly*<br/>
[içinde] Yalnızca okunur erişim için bir `CSettingsStore` nesnenin oluşturulup oluşturulmadığını belirleyen boolean parametresi.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan `CSettingsStore` nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

[CSettingsStoreSP::SetRuntimeClass](#setruntimeclass) yöntemini kullanarak ne tür bir `CSettingsStoreSP::Create` nesne oluşturacağını belirleyebilirsiniz. Varsayılan olarak, bu yöntem `CSettingsStore` bir nesne oluşturur.

Yönetici modunda `CSettingsStore` bir nesne oluşturursanız, tüm kayıt defteri erişimi için varsayılan konum HKEY_LOCAL_MACHINE. Aksi takdirde, tüm kayıt defteri erişimi için varsayılan konum HKEY_CURRENT_USER.

*bAdmin* DOĞRU ise, uygulama yönetim haklarına sahip olmalıdır. Aksi takdirde, kayıt defterine erişmeye çalıştığında başarısız olur.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın yönteminin `Create` nasıl `CSettingsStoreSP` kullanılacağını göstermektedir.

[!code-cpp[NVC_MFC_RibbonApp#33](../../mfc/reference/codesnippet/cpp/csettingsstoresp-class_1.cpp)]

## <a name="csettingsstorespcsettingsstoresp"></a><a name="csettingsstoresp"></a>CSettingsStoreSP::CsettingsStoreSP

[CSettingsStoreSP Sınıf](../../mfc/reference/csettingsstoresp-class.md) nesnesi oluşturur.

```
CSettingsStoreSP::CSettingsStoreSP(DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parametreler

*dwUserData*<br/>
[içinde] Nesnenin `CSettingsStoreSP` depolandığı kullanıcı tanımlı veriler.

### <a name="remarks"></a>Açıklamalar

Nesne, `CSettingsStoreSP` *dwUserData'daki* verileri korunan üye `m_dwUserData`değişkende depolar.

## <a name="csettingsstorespsetruntimeclass"></a><a name="setruntimeclass"></a>CSettingsStoreSP::SetRuntimeClass

Çalışma zamanı sınıfını ayarlar. [CSettingsStoreSP::Create](#create) yöntemi, ne tür bir nesne oluşturacaklarını belirlemek için çalışma zamanı sınıfını kullanır.

```
static BOOL __stdcall CSettingsStoreSP::SetRuntimeClass(CRuntimeClass* pRTI);
```

### <a name="parameters"></a>Parametreler

*pRTI*<br/>
[içinde] [CSettingsStore Sınıfı'ndan](../../mfc/reference/csettingsstore-class.md)türetilen bir sınıfın çalışma zamanı sınıf bilgilerine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Doğru eğer başarılı; *pRTI* ile tanımlanan sınıf türetilmiş `CSettingsStore`değilse FALSE.

### <a name="remarks"></a>Açıklamalar

[CSettingsStoreSP Sınıfını](../../mfc/reference/csettingsstoresp-class.md) kullanarak `CSettingsStore`. Türetilen `SetRuntimeClass` özel bir sınıfın nesnelerini oluşturmak istiyorsanız yöntemi kullanın. `CSettingsStore`

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CSettingsStore Sınıfı](../../mfc/reference/csettingsstore-class.md)
