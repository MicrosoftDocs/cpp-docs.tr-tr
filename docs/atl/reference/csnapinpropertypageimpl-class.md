---
title: Csnapınpropertypageımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl::CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl::CancelToClose
- ATLSNAP/ATL::CSnapInPropertyPageImpl::Create
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnApply
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnHelp
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnKillActive
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnQueryCancel
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnReset
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnSetActive
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardBack
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardFinish
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardNext
- ATLSNAP/ATL::CSnapInPropertyPageImpl::QuerySiblings
- ATLSNAP/ATL::CSnapInPropertyPageImpl::SetModified
- ATLSNAP/ATL::CSnapInPropertyPageImpl::m_psp
dev_langs:
- C++
helpviewer_keywords:
- snap-ins, property pages
- snap-ins
- property pages, ATL
- CSnapInPropertyPageImpl class
ms.assetid: 75bdce5a-985e-4166-bd44-493132e023c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c89f577168593dcb22570af63801fc05654eb4b3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100703"
---
# <a name="csnapinpropertypageimpl-class"></a>Csnapınpropertypageımpl sınıfı

Bu sınıf, bir ek özellik sayfa nesnesi uygulamak için yöntemler sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
CSnapInPropertyPageImpl : public CDialogImplBase
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSnapInPropertyPageImpl::CancelToClose](#canceltoclose)|Durumunun değiştiğini **Tamam** ve **iptal** düğmeleri.|
|[CSnapInPropertyPageImpl::Create](#create)|Yeni oluşturulan başlatır `CSnapInPropertyPageImpl` nesne.|
|[CSnapInPropertyPageImpl::OnApply](#onapply)|Kullanıcı tıkladığında framework tarafından çağırılır **şimdi Uygula** sihirbaz türü özellik sayfası kullanılırken düğmesi.|
|[CSnapInPropertyPageImpl::OnHelp](#onhelp)|Kullanıcı tıkladığında framework tarafından çağırılır **yardımcı** sihirbaz türü özellik sayfası kullanılırken düğmesi.|
|[CSnapInPropertyPageImpl::OnKillActive](#onkillactive)|Geçerli sayfa artık etkin olduğunda framework tarafından çağırılır.|
|[CSnapInPropertyPageImpl::OnQueryCancel](#onquerycancel)|Kullanıcı tıkladığında framework tarafından çağırılır **iptal** düğmesi ve iptal etme gerçekleşmemişken.|
|[CSnapInPropertyPageImpl::OnReset](#onreset)|Kullanıcı tıkladığında framework tarafından çağırılır **sıfırlama** sihirbaz türü özellik sayfası kullanılırken düğmesi.|
|[CSnapInPropertyPageImpl::OnSetActive](#onsetactive)|Geçerli sayfa etkin olduğunda framework tarafından çağırılır.|
|[CSnapInPropertyPageImpl::OnWizardBack](#onwizardback)|Kullanıcı tıkladığında framework tarafından çağırılır **geri** sihirbaz türü özellik sayfası kullanılırken düğmesi.|
|[CSnapInPropertyPageImpl::OnWizardFinish](#onwizardfinish)|Kullanıcı tıkladığında framework tarafından çağırılır **son** sihirbaz türü özellik sayfası kullanılırken düğmesi.|
|[CSnapInPropertyPageImpl::OnWizardNext](#onwizardnext)|Kullanıcı tıkladığında framework tarafından çağırılır **sonraki** sihirbaz türü özellik sayfası kullanılırken düğmesi.|
|[CSnapInPropertyPageImpl::QuerySiblings](#querysiblings)|Geçerli iletinin özellik sayfasının tüm sayfalara iletir.|
|[CSnapInPropertyPageImpl::SetModified](#setmodified)|Etkinleştirme veya devre dışı çağrı **şimdi Uygula** düğmesi.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CSnapInPropertyPageImpl::m_psp](#m_psp)|Windows `PROPSHEETPAGE` yapısı tarafından kullanılan `CSnapInPropertyPageImpl` nesne.|

## <a name="remarks"></a>Açıklamalar

`CSnapInPropertyPageImpl` bir ek özellik sayfa nesnesi için temel bir uygulamasını sağlar. Ek özellik sayfası temel özelliklerinde, birkaç farklı arabirimi kullanılarak uygulanır ve türleri eşleyin.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CDialogImplBase`

`CSnapInPropertyPageImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsnap.h

##  <a name="canceltoclose"></a>  CSnapInPropertyPageImpl::CancelToClose

Veriler bir kalıcı özellik sayfasının bir sayfa üzerinde kurtarılamaz bir değişiklik yapıldıktan sonra bu işlevi çağırın.

```
void CancelToClose();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev değiştirecek **Tamam** düğmesi **Kapat** ve devre dışı bırakma **iptal** düğmesi. Bu uyarılar kullanıcının kalıcı bir işlemdir ve değişiklikleri bir değişikliktir iptal edilemez değiştirin.

`CancelToClose` Üye işlev hiçbir şey yapmaz kalıcı olmayan özellik sayfası modelsiz bir özellik sayfası sahip olmadığından bir **iptal** varsayılan düğme.

##  <a name="csnapinpropertypageimpl"></a>  CSnapInPropertyPageImpl::CSnapInPropertyPageImpl

Oluşturur bir `CSnapInPropertyPageImpl` nesne.

```
CSnapInPropertyPageImpl(LPCTSTR lpszTitle = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszTitle*<br/>
[in] Özellik sayfasının başlığı.

### <a name="remarks"></a>Açıklamalar

Temelindeki başlatmak için çağrı [CSnapInPropertyPageImpl::Create](#create).

##  <a name="create"></a>  CSnapInPropertyPageImpl::Create

Temelindeki özellik sayfasını başlatmak için bu işlevi çağırın.

```
HPROPSHEETPAGE Create();
```

### <a name="return-value"></a>Dönüş Değeri

İçin bir tanıtıcı bir `PROPSHEETPAGE` yeni oluşturulan özellik sayfası özniteliklerini içeren yapısı.

### <a name="remarks"></a>Açıklamalar

İlk çağırmalıdır [CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl) bu işlevi çağırmadan önce.

##  <a name="m_psp"></a>  CSnapInPropertyPageImpl::m_psp

`m_psp` bir yapı üyeleri özelliklerini depolamak `PROPSHEETPAGE`.

```
PROPSHEETPAGE m_psp;
```

### <a name="remarks"></a>Açıklamalar

Bu yapı, oluşturduğu sonra bir özellik sayfasının görünümünü başlatmak için kullanın.

Bu grubun üyeleri listesi dahil olmak üzere, bu yapı hakkında daha fazla bilgi için bkz. [PROPSHEETPAGE](https://msdn.microsoft.com/library/aa815151) Windows SDK.

##  <a name="onapply"></a>  CSnapInPropertyPageImpl::OnApply

Kullanıcı tıkladığında bu üye işlevi çağrılan **Tamam** veya **şimdi Uygula** düğmesi.

```
BOOL OnApply();
```

### <a name="return-value"></a>Dönüş Değeri

Değişiklikler kabul edilirse sıfır; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Önce `OnApply` volat jen tehdy çerçeve tarafından çağrısı yapmanız gerekir `SetModified` ve onun parametresi TRUE olarak ayarlayın. Bu etkinleştirecek **şimdi Uygula** özellik sayfasında bir değişiklik kullanıcının yaptığı hemen sonra düğme.

Programınızı alan kullanıcı tıkladığında eylemi belirtmek için bu üye işlevi geçersiz kılma **şimdi Uygula** düğmesi. Geçersiz kılarken, işlev değişiklikleri kabul etmek için TRUE ve FALSE, değişiklikler etkili fotoğrafını çekmenizi engellemek için döndürmelidir.

Varsayılan uygulaması `OnApply` TRUE döndürür.

##  <a name="onhelp"></a>  CSnapInPropertyPageImpl::OnHelp

Kullanıcı tıkladığında bu üye işlevi çağrılan **yardımcı** özellik sayfası için düğmesi.

```
void OnHelp();
```

### <a name="remarks"></a>Açıklamalar

Özellik sayfası için Yardım görüntülemek için bu üye işlevini geçersiz kılar.

##  <a name="onkillactive"></a>  CSnapInPropertyPageImpl::OnKillActive

Sayfa artık etkin sayfa olduğunda, bu üye işlevi çağrılır.

```
BOOL OnKillActive();
```

### <a name="return-value"></a>Dönüş Değeri

Veriler başarıyla güncelleştirildi olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, özel veri doğrulama görevleri gerçekleştirmek için geçersiz kılın.

##  <a name="onquerycancel"></a>  CSnapInPropertyPageImpl::OnQueryCancel

Kullanıcı tıkladığında bu üye işlevi çağrılan **iptal** düğmesine tıklayın ve önce iptal etme eylemi devre dışı yapıldığının.

```
BOOL OnQueryCancel();
```

### <a name="return-value"></a>Dönüş Değeri

İptal işlemine izin vermek için sıfır olmayan; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Program alır kullanıcı tıkladığında bir eylem belirtmek için bu üye işlevi geçersiz kılma **iptal** düğmesi.

Varsayılan uygulaması `OnQueryCancel` TRUE döndürür.

##  <a name="onreset"></a>  CSnapInPropertyPageImpl::OnReset

Kullanıcı tıkladığında bu üye işlevi çağrılan **iptal** düğmesi.

```
void OnReset();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev çağrıldığında, daha önce tıklayarak kullanıcı tarafından yapılan tüm özellik sayfalarını değişikliklerini **şimdi Uygula** düğmesi atılır ve özellik sayfası odağını korur.

Program alır kullanıcı tıkladığında eylemi belirtmek için bu üye işlevi geçersiz kılma **iptal** düğmesi.

##  <a name="onsetactive"></a>  CSnapInPropertyPageImpl::OnSetActive

Sayfa kullanıcı tarafından seçilir ve etkin sayfa olur bu üye işlevi çağrılır.

```
BOOL OnSetActive();
```

### <a name="return-value"></a>Dönüş Değeri

Sayfa başarıyla active ayarlandığını olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi bir sayfa etkinleştirildiğinde görevleri gerçekleştirmek için geçersiz kılın. Bu üye işlevin geçersiz kılma, başka bir işlem yapılmadan önce varsayılan sürüm çağırmanız gerekir.

Varsayılan uygulama, TRUE döndürür.

##  <a name="onwizardback"></a>  CSnapInPropertyPageImpl::OnWizardBack

Kullanıcı tıkladığında bu üye işlevi çağrılan **geri** sihirbaz düğmesi.

```
BOOL OnWizardBack();
```

### <a name="return-value"></a>Dönüş Değeri

- otomatik olarak önceki sayfaya ilerlemek için 0'ı tıklatın.

- sayfayı değiştirmesini engellemek için -1.

Dışında bir sonraki sayfasına atlamak için görüntülenecek iletişim kutusunun tanımlayıcısını döndürür.

### <a name="remarks"></a>Açıklamalar

Kullanıcı ne zaman gerçekleştirmeniz gereken bazı eylemleri belirtmek için bu üye işlevi geçersiz kılma **geri** düğmesine tıklandığında.

##  <a name="onwizardfinish"></a>  CSnapInPropertyPageImpl::OnWizardFinish

Kullanıcı tıkladığında bu üye işlevi çağrılan **son** sihirbaz düğmesi.

```
BOOL OnWizardFinish();
```

### <a name="return-value"></a>Dönüş Değeri

Sihirbaz sona erdiğinde özellik sayfası yok olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Kullanıcı ne zaman gerçekleştirmeniz gereken bazı eylemleri belirtmek için bu üye işlevi geçersiz kılma **son** düğmesine tıklandığında.

##  <a name="onwizardnext"></a>  CSnapInPropertyPageImpl::OnWizardNext

Kullanıcı tıkladığında bu üye işlevi çağrılan **sonraki** sihirbaz düğmesi.

```
BOOL OnWizardNext();
```

### <a name="return-value"></a>Dönüş Değeri

- otomatik olarak bir sonraki sayfaya ilerlemek için 0'ı tıklatın.

- sayfayı değiştirmesini engellemek için -1.

Dışında bir sonraki sayfasına atlamak için görüntülenecek iletişim kutusunun tanımlayıcısını döndürür.

### <a name="remarks"></a>Açıklamalar

Kullanıcı ne zaman gerçekleştirmeniz gereken bazı eylemleri belirtmek için bu üye işlevi geçersiz kılma **sonraki** düğmesine tıklandığında.

##  <a name="querysiblings"></a>  CSnapInPropertyPageImpl::QuerySiblings

Özellik sayfasında her sayfa için bir ileti iletmek için bu üye işlevini çağırın.

```
LRESULT QuerySiblings(WPARAM wParam, LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*wParam*<br/>
[in] Ek ileti bağımlı bilgileri belirtir.

*lParam*<br/>
[in] Ek ileti bağımlı bilgileri belirtir.

### <a name="return-value"></a>Dönüş Değeri

İletiyi sonraki özellik sayfasına iletilmesi gereken değil olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Özellik sayfası bir sayfa sıfır olmayan bir değer döndürürse, iletiyi sonraki sayfalara göndermez.

##  <a name="setmodified"></a>  CSnapInPropertyPageImpl::SetModified

Etkinleştirmek veya devre dışı bırakmak için bu üye işlevi çağrısı **şimdi Uygula** özellik sayfası ayarları için uygun dış nesne uygulanmalıdır olup temel düğmesi.

```
void SetModified(BOOL bChanged = TRUE);
```

### <a name="parameters"></a>Parametreler

*bChanged*<br/>
[in] Özellik sayfası ayarları uygulanmış olan son daraltılmasından değiştirilmiş belirtmek için TRUE; Özellik sayfası ayarları uygulanmış veya yoksayılıp yoksayılmaması gerektiğini belirtmek için FALSE.

### <a name="remarks"></a>Açıklamalar

Özellik sayfası tutar izleme hangi sayfaların "kirli" diğer bir deyişle, kendisi için aradığınız özellik sayfaları `SetModified( TRUE )`. **Şimdi Uygula** düğmesi her zaman etkindir çağırırsanız `SetModified( TRUE )` birinin sayfaların. **Şimdi Uygula** düğmesini devre dışı bırakılacak çağırdığınızda `SetModified( FALSE )` yalnızca diğer sayfalardan hiçbiri "." kirli, ancak sayfalardan biri için

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
