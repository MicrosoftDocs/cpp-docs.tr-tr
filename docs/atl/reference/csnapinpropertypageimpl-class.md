---
title: CSnapInPropertyPageImpl Sınıfı
ms.date: 11/04/2016
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
helpviewer_keywords:
- snap-ins, property pages
- snap-ins
- property pages, ATL
- CSnapInPropertyPageImpl class
ms.assetid: 75bdce5a-985e-4166-bd44-493132e023c4
ms.openlocfilehash: 3f09e8500eadd36eec53db95f10261834d672101
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747585"
---
# <a name="csnapinpropertypageimpl-class"></a>CSnapInPropertyPageImpl Sınıfı

Bu sınıf, bir yapışma özelliği sayfası nesnesi uygulamak için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
CSnapInPropertyPageImpl : public CDialogImplBase
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSnapInPropertyPageImpl::CancelToClose](#canceltoclose)|**Tamam** ve **İptal** düğmelerinin durumunu değiştirir.|
|[CSnapInPropertyPageImpl::Oluştur](#create)|Yeni oluşturulan bir `CSnapInPropertyPageImpl` nesneyi başharfe ait hale leştirir.|
|[CSnapInPropertyPageImpl::OnApply](#onapply)|Kullanıcı sihirbaz türünde bir özellik sayfası kullanırken **Şimdi Uygula** düğmesini tıklattığında çerçeve tarafından çağrılır.|
|[CSnapInPropertyPageImpl::OnHelp](#onhelp)|Kullanıcı sihirbaz türünde bir özellik sayfası kullanırken **Yardım** düğmesini tıklattığında çerçeve tarafından çağrılır.|
|[CSnapInPropertyPageImpl::OnKillActive](#onkillactive)|Geçerli sayfa artık etkin olmadığında çerçeve tarafından çağrılır.|
|[CSnapInPropertyPageImpl::OnQueryCancel](#onquerycancel)|Kullanıcı **İptal** düğmesini tıklattığında ve iptal gerçekleşmeden önce çerçeve tarafından çağrılır.|
|[CSnapInPropertyPageImpl::OnReset](#onreset)|Kullanıcı sihirbaz türünde bir özellik sayfası kullanırken **Sıfırla** düğmesini tıklattığında çerçeve tarafından çağrılır.|
|[CSnapInPropertyPageImpl::OnSetActive](#onsetactive)|Geçerli sayfa etkin olduğunda çerçeve tarafından çağrılır.|
|[CSnapInPropertyPageImpl::OnWizardBack](#onwizardback)|Kullanıcı sihirbaz türünde bir özellik sayfası kullanırken **Geri düğmesini** tıklattığında çerçeve tarafından çağrılır.|
|[CSnapInPropertyPageImpl::OnWizardFinish](#onwizardfinish)|Kullanıcı sihirbaz türünde bir özellik sayfası kullanırken **Finish** düğmesini tıklattığında çerçeve tarafından çağrılır.|
|[CSnapInPropertyPageImpl::OnWizardNext](#onwizardnext)|Kullanıcı sihirbaz türünde bir özellik sayfası kullanırken **İleri** düğmesini tıklattığında çerçeve tarafından çağrılır.|
|[CSnapInPropertyPageImpl::QuerySiblings](#querysiblings)|Geçerli iletiyi özellik sayfasının tüm sayfalarına iletir.|
|[CSnapInPropertyPageImpl::SetModi](#setmodified)|**Şimdi Uygula** düğmesini etkinleştirmek veya devre dışı bırakmak için arayın.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CSnapInPropertyPageImpl::m_psp](#m_psp)|Nesne `PROPSHEETPAGE` tarafından kullanılan Windows yapısı. `CSnapInPropertyPageImpl`|

## <a name="remarks"></a>Açıklamalar

`CSnapInPropertyPageImpl`bir yapışma özelliği sayfası nesnesi için temel bir uygulama sağlar. Bir snap-in özellik sayfasının temel özellikleri birkaç farklı arabirim ve harita türleri kullanılarak uygulanır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CDialogImplBase`

`CSnapInPropertyPageImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsnap.h

## <a name="csnapinpropertypageimplcanceltoclose"></a><a name="canceltoclose"></a>CSnapInPropertyPageImpl::CancelToClose

Modal özellik sayfasının bir sayfasındaki verilerde kurtarılamaz bir değişiklik yapıldıktan sonra bu işlevi arayın.

```cpp
void CancelToClose();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev **Tamam** düğmesini **Kapat** düğmesine değiştirir ve **İptal** düğmesini devre dışı eder. Bu değişiklik, kullanıcıyı bir değişikliğin kalıcı olduğu ve değişikliklerin iptal edilemeyeceği konusunda uyarır.

Modeless özellik sayfasında varsayılan olarak `CancelToClose` **İptal** düğmesi olmadığından, üye işlev modeless özellik sayfasında hiçbir şey yapmaz.

## <a name="csnapinpropertypageimplcsnapinpropertypageimpl"></a><a name="csnapinpropertypageimpl"></a>CSnapInPropertyPageImpl::CSnapInPropertyPageImpl

Bir `CSnapInPropertyPageImpl` nesne inşa eder.

```
CSnapInPropertyPageImpl(LPCTSTR lpszTitle = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszTitle*<br/>
[içinde] Özellik sayfasının başlığı.

### <a name="remarks"></a>Açıklamalar

Alttaki yapıyı başlatmak için [CSnapInPropertyPageImpl'i arayın::Oluştur](#create).

## <a name="csnapinpropertypageimplcreate"></a><a name="create"></a>CSnapInPropertyPageImpl::Oluştur

Özellik sayfasının temel yapısını başlatmak için bu işlevi arayın.

```
HPROPSHEETPAGE Create();
```

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan `PROPSHEETPAGE` özellik sayfasının özniteliklerini içeren bir yapının tutamacı.

### <a name="remarks"></a>Açıklamalar

Bu işlevi aramadan önce [CSnapInPropertyPageImpl::CSnapInPropertyPageImpl'i](#csnapinpropertypageimpl) aramalısınız.

## <a name="csnapinpropertypageimplm_psp"></a><a name="m_psp"></a>CSnapInPropertyPageImpl::m_psp

`m_psp`üyelerinin özelliklerini depolayan bir `PROPSHEETPAGE`yapıdır.

```
PROPSHEETPAGE m_psp;
```

### <a name="remarks"></a>Açıklamalar

Bir özellik sayfasının oluşturulduktan sonra görünümünü başlatmayı sağlamak için bu yapıyı kullanın.

Üyelerinin listesi de dahil olmak üzere bu yapı hakkında daha fazla bilgi için Windows SDK'daki [PROPSHEETPAGE](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v3) sayfasına bakın.

## <a name="csnapinpropertypageimplonapply"></a><a name="onapply"></a>CSnapInPropertyPageImpl::OnApply

Kullanıcı **Tamam** veya **Şimdi Uygula** düğmesini tıklattığında bu üye işlev çağrılır.

```
BOOL OnApply();
```

### <a name="return-value"></a>Dönüş Değeri

Değişiklikler kabul edilirse sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Çerçeve `OnApply` tarafından çağrılmadan önce, parametresini arayıp `SetModified` TRUE olarak ayarlamış olmalısınız. Bu, kullanıcı özellik sayfasında değişiklik yapar etmez **Şimdi Uygula** düğmesini etkinleştirecektir.

Kullanıcı **Şimdi Uygula** düğmesini tıklattığında programınızın hangi eylemi yaptığını belirtmek için bu üye işlevini geçersiz kılın. Geçersiz kılınırken, işlev değişiklikleri kabul etmek için TRUE ve değişikliklerin etkili olmasını önlemek için FALSE döndürmelidir.

True döndürür `OnApply` varsayılan uygulaması.

## <a name="csnapinpropertypageimplonhelp"></a><a name="onhelp"></a>CSnapInPropertyPageImpl::OnHelp

Kullanıcı özellik sayfası için **Yardım** düğmesini tıklattığında bu üye işlev çağrılır.

```cpp
void OnHelp();
```

### <a name="remarks"></a>Açıklamalar

Özellik sayfası için yardım görüntülemek için bu üye işlevini geçersiz kılın.

## <a name="csnapinpropertypageimplonkillactive"></a><a name="onkillactive"></a>CSnapInPropertyPageImpl::OnKillActive

Bu üye işlev, sayfa artık etkin sayfa olmadığında çağrılır.

```
BOOL OnKillActive();
```

### <a name="return-value"></a>Dönüş Değeri

Veriler başarıyla güncelleştirildiyse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Özel veri doğrulama görevleri gerçekleştirmek için bu üye işlevi geçersiz kılın.

## <a name="csnapinpropertypageimplonquerycancel"></a><a name="onquerycancel"></a>CSnapInPropertyPageImpl::OnQueryCancel

Bu üye işlevi, kullanıcı **İptal** düğmesini tıklattığında ve iptal eylemi gerçekleşmeden önce çağrılır.

```
BOOL OnQueryCancel();
```

### <a name="return-value"></a>Dönüş Değeri

İptal işlemine izin vermek için sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kullanıcı **İptal** düğmesini tıklattığında programın aldığı bir eylemi belirtmek için bu üye işlevini geçersiz kılın.

True döndürür `OnQueryCancel` varsayılan uygulaması.

## <a name="csnapinpropertypageimplonreset"></a><a name="onreset"></a>CSnapInPropertyPageImpl::OnReset

Kullanıcı **İptal** düğmesini tıklattığında bu üye işlev çağrılır.

```cpp
void OnReset();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev çağrıldığında, kullanıcı tarafından daha önce **Şimdi Uygula** düğmesini tıklatarak yapılan tüm özellik sayfalarındayapılan değişiklikler atılır ve özellik sayfası odağı korur.

Kullanıcı **İptal** düğmesini tıklattığında programın hangi eylemi yaptığını belirtmek için bu üye işlevini geçersiz kılın.

## <a name="csnapinpropertypageimplonsetactive"></a><a name="onsetactive"></a>CSnapInPropertyPageImpl::OnSetActive

Bu üye işlev, sayfa kullanıcı tarafından seçildiğinde ve etkin sayfa olduğunda çağrılır.

```
BOOL OnSetActive();
```

### <a name="return-value"></a>Dönüş Değeri

Sayfa başarıyla etkin olarak ayarlanmışsa sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir sayfa etkinleştirildiğinde görevleri gerçekleştirmek için bu üye işlevi geçersiz kılın. Bu üye işlevin geçersiz kılınması, başka bir işlem yapılmadan önce varsayılan sürümü aramalıdır.

Varsayılan uygulama TRUE döndürür.

## <a name="csnapinpropertypageimplonwizardback"></a><a name="onwizardback"></a>CSnapInPropertyPageImpl::OnWizardBack

Bu üye işlev, kullanıcı bir sihirbazda **Geri Düğmesini** tıklattığında çağrılır.

```
BOOL OnWizardBack();
```

### <a name="return-value"></a>Dönüş Değeri

- 0 otomatik olarak önceki sayfaya ilerlemek için.

- -1 sayfanın değişmesini önlemek için.

Bir sonrakisayfadan başka bir sayfaya atlamak için, görüntülenecek iletişim kutusunun tanımlayıcısını döndürün.

### <a name="remarks"></a>Açıklamalar

**Geri** düğmesine tıklandığında kullanıcının yapması gereken bazı eylemlerbelirtmek için bu üye işlevini geçersiz kılın.

## <a name="csnapinpropertypageimplonwizardfinish"></a><a name="onwizardfinish"></a>CSnapInPropertyPageImpl::OnWizardFinish

Kullanıcı bir sihirbazda **Finish** düğmesini tıklattığında bu üye işlev çağrılır.

```
BOOL OnWizardFinish();
```

### <a name="return-value"></a>Dönüş Değeri

Sihirbaz bittiğinde özellik sayfası yok edilirse sıfırolmayan; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

**Bitiş** düğmesi tıklatıldığında kullanıcının yapması gereken bazı eylemlerbelirtmek için bu üye işlevini geçersiz kılın.

## <a name="csnapinpropertypageimplonwizardnext"></a><a name="onwizardnext"></a>CSnapInPropertyPageImpl::OnWizardNext

Bu üye işlev, kullanıcı bir sihirbazda **İleri** düğmesini tıklattığında çağrılır.

```
BOOL OnWizardNext();
```

### <a name="return-value"></a>Dönüş Değeri

- 0 otomatik olarak bir sonraki sayfaya ilerlemek için.

- -1 sayfanın değişmesini önlemek için.

Bir sonrakisayfadan başka bir sayfaya atlamak için, görüntülenecek iletişim kutusunun tanımlayıcısını döndürün.

### <a name="remarks"></a>Açıklamalar

**İleri** düğmesine tıklandığında kullanıcının yapması gereken bazı eylemlerbelirtmek için bu üye işlevini geçersiz kılın.

## <a name="csnapinpropertypageimplquerysiblings"></a><a name="querysiblings"></a>CSnapInPropertyPageImpl::QuerySiblings

Özellik sayfasındaki her sayfaya bir ileti iletmek için bu üye işlevini arayın.

```
LRESULT QuerySiblings(WPARAM wParam, LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*Wparam*<br/>
[içinde] İletiye bağımlı ek bilgileri belirtir.

*Lparam*<br/>
[içinde] İletiye bağımlı ek bilgileri belirtir.

### <a name="return-value"></a>Dönüş Değeri

İleti bir sonraki özellik sayfasına iletilmezse sıfıra inmez; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

Bir sayfa sıfır olmayan bir değer döndürürse, özellik sayfası iletiyi sonraki sayfalara göndermez.

## <a name="csnapinpropertypageimplsetmodified"></a><a name="setmodified"></a>CSnapInPropertyPageImpl::SetModi

Özellik sayfasındaki ayarların uygun dış nesneye uygulanıp uygulanmayacağına bağlı olarak **Şimdi Uygula** düğmesini etkinleştirmek veya devre dışı etmek için bu üye işlevini arayın.

```cpp
void SetModified(BOOL bChanged = TRUE);
```

### <a name="parameters"></a>Parametreler

*b Değiştirildi*<br/>
[içinde] Özellik sayfası ayarlarının son uygulandığından beri değiştirildiğini belirtmek için TRUE; Özellik sayfası ayarlarının uygulandığını veya yoksayılması gerektiğini belirtmek için FALSE.

### <a name="remarks"></a>Açıklamalar

Özellik sayfası, hangi sayfaların "kirli" olduğunu, yani çağırdığınız `SetModified( TRUE )`özellik sayfalarını izler. Sayfalardan birini ararsanız `SetModified( TRUE )` Şimdi **Uygula** düğmesi her zaman etkinleştirilir. **Şimdi Uygula** düğmesi, sayfalardan `SetModified( FALSE )` birini aradiğinizde, ancak diğer sayfaların hiçbiri "kirli" değilse devre dışı bırakılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
