---
description: 'Daha fazla bilgi edinin: CSnapInPropertyPageImpl sınıfı'
title: CSnapInPropertyPageImpl sınıfı
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
ms.openlocfilehash: c3699dff31291525638f128382ad39369f18deca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140549"
---
# <a name="csnapinpropertypageimpl-class"></a>CSnapInPropertyPageImpl sınıfı

Bu sınıf, bir ek bileşen özellik sayfası nesnesi uygulamak için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
CSnapInPropertyPageImpl : public CDialogImplBase
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSnapInPropertyPageImpl:: CSnapInPropertyPageImpl](#csnapinpropertypageimpl)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSnapInPropertyPageImpl:: CancelToClose](#canceltoclose)|**Tamam** ve **iptal** düğmelerinin durumunu değiştirir.|
|[CSnapInPropertyPageImpl:: Create](#create)|Yeni oluşturulan bir `CSnapInPropertyPageImpl` nesneyi başlatır.|
|[CSnapInPropertyPageImpl:: OnApply](#onapply)|Kullanıcı, sihirbaz türü özellik sayfası kullanırken **Şimdi Uygula** düğmesine tıkladığında Framework tarafından çağırılır.|
|[CSnapInPropertyPageImpl:: OnHelp](#onhelp)|Kullanıcı, sihirbaz türü özellik sayfası kullanırken **Yardım** düğmesine tıkladığında Framework tarafından çağırılır.|
|[CSnapInPropertyPageImpl:: OnKillActive](#onkillactive)|Geçerli sayfa artık etkin olmadığında Framework tarafından çağırılır.|
|[CSnapInPropertyPageImpl:: OnQueryCancel](#onquerycancel)|Kullanıcı **iptal** düğmesine tıkladığında ve iptal gerçekleşmeden önce Framework tarafından çağırılır.|
|[CSnapInPropertyPageImpl:: OnReset](#onreset)|Kullanıcı, sihirbaz türü özellik sayfası kullanırken **sıfırlama** düğmesine tıkladığında Framework tarafından çağırılır.|
|[CSnapInPropertyPageImpl:: OnSetActive](#onsetactive)|Geçerli sayfa etkin hale geldiğinde Framework tarafından çağırılır.|
|[CSnapInPropertyPageImpl:: OnWizardBack](#onwizardback)|Kullanıcı bir sihirbaz türü özellik sayfası kullanırken **geri** düğmesine tıkladığında Framework tarafından çağırılır.|
|[CSnapInPropertyPageImpl:: Onwizardtamamlaya](#onwizardfinish)|Kullanıcı, sihirbaz türü özellik sayfası kullanırken **son** düğmesine tıkladığında Framework tarafından çağırılır.|
|[CSnapInPropertyPageImpl:: OnWizardNext](#onwizardnext)|Kullanıcı bir sihirbaz türü özellik sayfası kullanırken **İleri** düğmesine tıkladığında Framework tarafından çağırılır.|
|[CSnapInPropertyPageImpl:: Queryeşdüzey değerleri](#querysiblings)|Geçerli iletiyi Özellik sayfasının tüm sayfalarına iletir.|
|[CSnapInPropertyPageImpl:: SetModified](#setmodified)|**Şimdi Uygula** düğmesini etkinleştirmek veya devre dışı bırakmak için çağırın.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CSnapInPropertyPageImpl:: m_psp](#m_psp)|`PROPSHEETPAGE`Nesnesi tarafından kullanılan Windows yapısı `CSnapInPropertyPageImpl` .|

## <a name="remarks"></a>Açıklamalar

`CSnapInPropertyPageImpl` ek bileşen özellik sayfası nesnesi için temel bir uygulama sağlar. Ek bileşen özelliği sayfasının temel özellikleri birkaç farklı arabirim ve eşleme türü kullanılarak uygulanır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CDialogImplBase`

`CSnapInPropertyPageImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsnap. h

## <a name="csnapinpropertypageimplcanceltoclose"></a><a name="canceltoclose"></a> CSnapInPropertyPageImpl:: CancelToClose

Kalıcı bir özellik sayfasının sayfasındaki verilerde kurtarılamaz bir değişiklik yapıldıktan sonra bu işlevi çağırın.

```cpp
void CancelToClose();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, **Kapat düğmesini kapatmak** ve **iptal** düğmesini devre dışı bırakmak için **Tamam** düğmesini değiştirecek. Bu değişiklik, kullanıcıyı bir değişikliğin kalıcı olduğunu ve değişikliklerin iptal edilemez olduğunu uyarır.

Kalıcı olmayan özellik sayfasında `CancelToClose` Varsayılan olarak bir **iptal** düğmesi bulunmadığından, üye işlevi modsuz bir özellik sayfasında hiçbir şey yapmaz.

## <a name="csnapinpropertypageimplcsnapinpropertypageimpl"></a><a name="csnapinpropertypageimpl"></a> CSnapInPropertyPageImpl:: CSnapInPropertyPageImpl

Bir `CSnapInPropertyPageImpl` nesnesi oluşturur.

```
CSnapInPropertyPageImpl(LPCTSTR lpszTitle = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszTitle*<br/>
'ndaki Özellik sayfasının başlığı.

### <a name="remarks"></a>Açıklamalar

Temel yapıyı başlatmak için [CSnapInPropertyPageImpl:: Create](#create)çağırın.

## <a name="csnapinpropertypageimplcreate"></a><a name="create"></a> CSnapInPropertyPageImpl:: Create

Özellik sayfasının temel yapısını başlatmak için bu işlevi çağırın.

```
HPROPSHEETPAGE Create();
```

### <a name="return-value"></a>Dönüş Değeri

`PROPSHEETPAGE`Yeni oluşturulan Özellik sayfasının özniteliklerini içeren bir yapıya yönelik bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu işlevi çağırmadan önce [CSnapInPropertyPageImpl:: CSnapInPropertyPageImpl](#csnapinpropertypageimpl) öğesini çağırmanız gerekir.

## <a name="csnapinpropertypageimplm_psp"></a><a name="m_psp"></a> CSnapInPropertyPageImpl:: m_psp

`m_psp` üyeleri, özelliklerini depolayan bir yapıdır `PROPSHEETPAGE` .

```
PROPSHEETPAGE m_psp;
```

### <a name="remarks"></a>Açıklamalar

Bir özellik sayfasının oluşturulduktan sonra görünümünü başlatmak için bu yapıyı kullanın.

Üyelerinin bir listesi de dahil olmak üzere bu yapı hakkında daha fazla bilgi için, Windows SDK [propsheetpage sayfasına](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v3) bakın.

## <a name="csnapinpropertypageimplonapply"></a><a name="onapply"></a> CSnapInPropertyPageImpl:: OnApply

Bu üye işlevi, Kullanıcı **Tamam** ' a veya **Şimdi Uygula** düğmesine tıkladığında çağrılır.

```
BOOL OnApply();
```

### <a name="return-value"></a>Dönüş Değeri

Değişiklikler kabul edilirse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`OnApply`Framework tarafından çağrılabilmesi için önce çağrılmalıdır `SetModified` parametresini true olarak ayarlamanız gerekir. Bu işlem, Kullanıcı Özellik sayfasında bir değişiklik yaptığında **Şimdi Uygula** düğmesini etkinleştirir.

Kullanıcı **Şimdi Uygula** düğmesine tıkladığında programınızın hangi eyleme uygulanacağını belirtmek için bu üye işlevi geçersiz kılın. Geçersiz kıldığınızda, değişikliklerin etkili olmasını engellemek için, işlevi değişiklikleri kabul etmek için TRUE, FALSE değerini döndürmelidir.

Varsayılan uygulama, `OnApply` true döndürür.

## <a name="csnapinpropertypageimplonhelp"></a><a name="onhelp"></a> CSnapInPropertyPageImpl:: OnHelp

Bu üye işlevi, Kullanıcı özellik sayfası için **Yardım** düğmesine tıkladığında çağrılır.

```cpp
void OnHelp();
```

### <a name="remarks"></a>Açıklamalar

Özellik sayfası için Yardımı göstermek üzere bu üye işlevini geçersiz kılın.

## <a name="csnapinpropertypageimplonkillactive"></a><a name="onkillactive"></a> CSnapInPropertyPageImpl:: OnKillActive

Bu üye işlevi, sayfa artık etkin sayfa olmadığında çağrılır.

```
BOOL OnKillActive();
```

### <a name="return-value"></a>Dönüş Değeri

Veriler başarıyla güncellendiyse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Özel veri doğrulama görevlerini gerçekleştirmek için bu üye işlevini geçersiz kılın.

## <a name="csnapinpropertypageimplonquerycancel"></a><a name="onquerycancel"></a> CSnapInPropertyPageImpl:: OnQueryCancel

Bu üye işlevi, Kullanıcı **iptal** düğmesine tıkladığında ve iptal etme eylemi gerçekleşmeden önce çağrılır.

```
BOOL OnQueryCancel();
```

### <a name="return-value"></a>Dönüş Değeri

İptal işlemine izin vermek için sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kullanıcı **iptal** düğmesine tıkladığında programın yapacağı bir eylem belirtmek için bu üye işlevi geçersiz kılın.

Varsayılan uygulama, `OnQueryCancel` true döndürür.

## <a name="csnapinpropertypageimplonreset"></a><a name="onreset"></a> CSnapInPropertyPageImpl:: OnReset

Bu üye işlevi, Kullanıcı **iptal** düğmesine tıkladığında çağrılır.

```cpp
void OnReset();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev çağrıldığında, Kullanıcı tarafından daha önce **Uygula** düğmesine tıklanacak olan tüm özellik sayfalarında yapılan değişiklikler atılır ve özellik sayfası odağı korur.

Kullanıcı **iptal** düğmesine tıkladığında programın hangi eylemi aldığını belirtmek için bu üye işlevi geçersiz kılın.

## <a name="csnapinpropertypageimplonsetactive"></a><a name="onsetactive"></a> CSnapInPropertyPageImpl:: OnSetActive

Bu üye işlevi, sayfa Kullanıcı tarafından seçildiğinde çağrılır ve etkin sayfa olur.

```
BOOL OnSetActive();
```

### <a name="return-value"></a>Dönüş Değeri

Sayfa başarıyla etkin ayarlandıysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir sayfa etkinleştirildiğinde görevleri gerçekleştirmek için bu üye işlevini geçersiz kılın. Bu üye işlevin geçersiz kılınması, diğer herhangi bir işlem yapılmadan önce varsayılan sürümü çağırmalıdır.

Varsayılan uygulama TRUE değerini döndürür.

## <a name="csnapinpropertypageimplonwizardback"></a><a name="onwizardback"></a> CSnapInPropertyPageImpl:: OnWizardBack

Bu üye işlevi, Kullanıcı bir sihirbazda **geri** düğmesine tıkladığında çağrılır.

```
BOOL OnWizardBack();
```

### <a name="return-value"></a>Dönüş Değeri

- önceki sayfaya otomatik olarak ilerlemek için 0.

- -1 sayfanın değiştirilmesini engellemek için.

Sonraki bir sayfaya geçmek için, görüntülenecek iletişim kutusunun tanımlayıcısını döndürün.

### <a name="remarks"></a>Açıklamalar

**Geri** düğmesine tıklandığında kullanıcının yapması gereken eylemi belirtmek için bu üye işlevi geçersiz kılın.

## <a name="csnapinpropertypageimplonwizardfinish"></a><a name="onwizardfinish"></a> CSnapInPropertyPageImpl:: Onwizardtamamlaya

Bu üye işlevi, Kullanıcı sihirbazın **son** düğmesine tıkladığında çağrılır.

```
BOOL OnWizardFinish();
```

### <a name="return-value"></a>Dönüş Değeri

Sihirbaz tamamlandığında Özellik sayfası yok edildiğinde sıfır dışında; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

**Son** düğmesine tıklandığında kullanıcının yapması gereken eylemi belirtmek için bu üye işlevi geçersiz kılın.

## <a name="csnapinpropertypageimplonwizardnext"></a><a name="onwizardnext"></a> CSnapInPropertyPageImpl:: OnWizardNext

Bu üye işlevi, Kullanıcı bir sihirbazda **İleri** düğmesine tıkladığında çağrılır.

```
BOOL OnWizardNext();
```

### <a name="return-value"></a>Dönüş Değeri

- sonraki sayfaya otomatik olarak ilerlemek için 0.

- -1 sayfanın değiştirilmesini engellemek için.

Sonraki bir sayfaya geçmek için, görüntülenecek iletişim kutusunun tanımlayıcısını döndürün.

### <a name="remarks"></a>Açıklamalar

**İleri** düğmesine tıklandığında kullanıcının yapması gereken eylemi belirtmek için bu üye işlevi geçersiz kılın.

## <a name="csnapinpropertypageimplquerysiblings"></a><a name="querysiblings"></a> CSnapInPropertyPageImpl:: Queryeşdüzey değerleri

Özellik sayfasındaki her sayfaya bir ileti iletmek için bu üye işlevini çağırın.

```
LRESULT QuerySiblings(WPARAM wParam, LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*wParam*<br/>
'ndaki İleti ile bağımlı ek bilgileri belirtir.

*lParam*<br/>
'ndaki İleti ile bağımlı ek bilgileri belirtir.

### <a name="return-value"></a>Dönüş Değeri

İleti bir sonraki özellik sayfasına iletilmemelidir. Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Bir sayfa sıfır dışında bir değer döndürürse, özellik sayfası iletiyi sonraki sayfalara göndermez.

## <a name="csnapinpropertypageimplsetmodified"></a><a name="setmodified"></a> CSnapInPropertyPageImpl:: SetModified

Özellik sayfasındaki ayarların uygun dış nesneye uygulanıp uygulanamayacağını temel alarak **Şimdi Uygula** düğmesini etkinleştirmek veya devre dışı bırakmak için bu üye işlevi çağırın.

```cpp
void SetModified(BOOL bChanged = TRUE);
```

### <a name="parameters"></a>Parametreler

*bChanged*<br/>
'ndaki Özellik sayfası ayarlarının, son uygulanma zamanından bu yana değiştirildiğini belirtmek için TRUE; Özellik sayfası ayarlarının uygulandığını göstermek için FALSE veya yok sayılacak olmalıdır.

### <a name="remarks"></a>Açıklamalar

Özellik sayfası hangi sayfaların "kirli,", yani hangi özellik sayfaları olduğunu izler `SetModified( TRUE )` . Sayfadan birini çağırırsanız, **Şimdi Uygula** düğmesi her zaman etkinleştirilecek `SetModified( TRUE )` .  `SetModified( FALSE )` Bir sayfadan birini çağırdığınızda, ancak yalnızca diğer sayfalardan hiçbiri "kirli" değilse, şimdi Uygula düğmesi devre dışı bırakılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
