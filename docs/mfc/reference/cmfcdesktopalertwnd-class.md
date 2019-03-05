---
title: CMFCDesktopAlertWnd sınıfı
ms.date: 10/18/2018
f1_keywords:
- CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::Create
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetCaptionHeight
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetDialogSize
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetLastPos
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetTransparency
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::HasSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnBeforeShow
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnClickLinkButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnDraw
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::ProcessCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetTransparency
helpviewer_keywords:
- CMFCDesktopAlertWnd [MFC], Create
- CMFCDesktopAlertWnd [MFC], GetAnimationSpeed
- CMFCDesktopAlertWnd [MFC], GetAnimationType
- CMFCDesktopAlertWnd [MFC], GetAutoCloseTime
- CMFCDesktopAlertWnd [MFC], GetCaptionHeight
- CMFCDesktopAlertWnd [MFC], GetDialogSize
- CMFCDesktopAlertWnd [MFC], GetLastPos
- CMFCDesktopAlertWnd [MFC], GetTransparency
- CMFCDesktopAlertWnd [MFC], HasSmallCaption
- CMFCDesktopAlertWnd [MFC], OnBeforeShow
- CMFCDesktopAlertWnd [MFC], OnClickLinkButton
- CMFCDesktopAlertWnd [MFC], OnCommand
- CMFCDesktopAlertWnd [MFC], OnDraw
- CMFCDesktopAlertWnd [MFC], ProcessCommand
- CMFCDesktopAlertWnd [MFC], SetAnimationSpeed
- CMFCDesktopAlertWnd [MFC], SetAnimationType
- CMFCDesktopAlertWnd [MFC], SetAutoCloseTime
- CMFCDesktopAlertWnd [MFC], SetSmallCaption
- CMFCDesktopAlertWnd [MFC], SetTransparency
ms.assetid: 73a2dd7b-ea84-4ae2-9830-7cf6e8dd2425
ms.openlocfilehash: 6b7d72b048d9f44233f96a3af859315ea20e9747
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57291645"
---
# <a name="cmfcdesktopalertwnd-class"></a>CMFCDesktopAlertWnd sınıfı

`CMFCDesktopAlertWnd` Sınıfı, bir olay hakkında kullanıcıyı bilgilendirmek üzere ekranda görüntülenen modsuz iletişim kutusu işlevselliğini uygular.

Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.
## <a name="syntax"></a>Sözdizimi

```
class CMFCDesktopAlertWnd : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCDesktopAlertWnd::Create](#create)|Oluşturur ve Masaüstü Uyarısı açılır penceresi başlatır.|
|[CMFCDesktopAlertWnd::GetAnimationSpeed](#getanimationspeed)|Animasyon hızı döndürür.|
|[CMFCDesktopAlertWnd::GetAnimationType](#getanimationtype)|Animasyon türü döndürür.|
|[CMFCDesktopAlertWnd::GetAutoCloseTime](#getautoclosetime)|Otomatik kapatma zaman aşımı döndürür.|
|[CMFCDesktopAlertWnd::GetCaptionHeight](#getcaptionheight)|Açıklamalı alt yazı yüksekliğini döndürür.|
|[CMFCDesktopAlertWnd::GetDialogSize](#getdialogsize)||
|[CMFCDesktopAlertWnd::GetLastPos](#getlastpos)|Ekranda Masaüstü Uyarısı açılır penceresi son geçerli konumunu döndürür.|
|[CMFCDesktopAlertWnd::GetTransparency](#gettransparency)|Saydamlık düzeyini döndürür.|
|[CMFCDesktopAlertWnd::HasSmallCaption](#hassmallcaption)|Masaüstü Uyarısı açılır penceresi ile küçük resim yazısı görüntülenip görüntülenmeyeceğini belirler.|
|[CMFCDesktopAlertWnd::OnBeforeShow](#onbeforeshow)||
|[CMFCDesktopAlertWnd::OnClickLinkButton](#onclicklinkbutton)|Kullanıcının Masaüstü uyarı menüsünde bulunan bir bağlantı düğmesine tıkladığında framework tarafından çağırılır.|
|[CMFCDesktopAlertWnd::OnCommand](#oncommand)|Kullanıcı bir öğeyi bir menüden bir alt denetimin bir bildirim iletisi gönderir veya bir kısayol tuş vuruşu çevrildiğinde seçtiğinde framework bu üye işlevini çağırır. (Geçersiz kılmaları [CWnd::OnCommand](../../mfc/reference/cwnd-class.md#oncommand).)|
|[CMFCDesktopAlertWnd::OnDraw](#ondraw)||
|[CMFCDesktopAlertWnd::ProcessCommand](#processcommand)||
|[CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed)|Yeni animasyon hızı ayarlar.|
|[CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype)|Animasyon türünü ayarlar.|
|[CMFCDesktopAlertWnd::SetAutoCloseTime](#setautoclosetime)|Otomatik kapatma zaman aşımı ayarlar.|
|[CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption)|Açıklamalı alt yazılar küçük ve normal arasında geçiş yapar.|
|[CMFCDesktopAlertWnd::SetTransparency](#settransparency)|Saydamlık düzeyini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bir Masaüstü Uyarısı açılır penceresi saydam olabilir, animasyon efektleri ile görünebilir ve (belirtilen gecikme sonrasında veya kullanıcı tarafından Kapat düğmesine tıklayarak kapatılana) kaybolabilir.

Bir Masaüstü Uyarısı açılır penceresi sırayla bir simge, ileti metni (bir etiketi) ve bir bağlantı içeren bir varsayılan iletişim de içerebilir. Alternatif olarak, bir Masaüstü Uyarısı açılır penceresi uygulamanın kaynaklardan özel bir iletişim kutusu içerebilir.

Bir Masaüstü Uyarısı açılır penceresi iki adımda oluşturduğunuz. İlk olarak oluşturmak için oluşturucu çağrısı `CMFCDesktopAlertWnd` nesne. İkinci olarak, çağrı [CMFCDesktopAlertWnd::Create](#create) penceresi oluştur ve buna eklemek için üye işlevini `CMFCDesktopAlertWnd` nesne.

`CMFCDesktopAlertWnd` Masaüstü Uyarısı açılır penceresi istemci alanını dolduran bir özel alt iletişim kutusu oluşturur. İletişim kutusu üzerinde konumlandırılmış tüm denetimler sahip.

Açılan pencerede özel bir iletişim kutusu görüntülemek için aşağıdaki adımları izleyin:

1. Öğesinden bir sınıf türetin `CMFCDesktopAlertDialog`.

1. Alt iletişim kutusu şablondan kaynakları oluşturun.

1. Çağrı [CMFCDesktopAlertWnd::Create](#create) iletişim kutusu şablonu ve çalışma zamanı sınıf bilgileri türetilmiş sınıfın bir işaretçisi kaynak Kimliğini kullanıyor.

1. Bu bildirimleri doğrudan işlemek için barındırılan denetimleri program veya program barındırılan denetimlerden gelen tüm bildirimler işlemek için özel bir iletişim kutusu.

Masaüstü Uyarısı açılır penceresi davranışını denetlemek için aşağıdaki işlevleri kullanın:

- Çağırarak, animasyon türü ayarlayın [CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype). Geçerli seçenekler şunlardır düzleştirme, slayt ve Soldurma.

- Çağırarak animasyon kare hızını ayarlamak [CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed).

- Çağırarak saydamlık düzeyi [CMFCDesktopAlertWnd::SetTransparency](#settransparency).

- Çağırarak açıklamalı alt yazı boyutunu değiştirmek için küçük [CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption). Küçük resim yazısı 7 piksel yüksekliğinde ' dir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, çeşitli yöntemlerin nasıl kullanılacağını gösterir `CMFCDesktopAlertWnd` yapılandırmak için sınıf bir `CMFCDesktopAlertWnd` nesne. Örneğin, bir animasyon türü ayarlayın, açılan pencerenin saydamlığı ayarlayın, uyarı pencere bir küçük resim yazısı görüntüler belirtin ve uyarı penceresi otomatik olarak kapanmadan önce geçen süreyi ayarlamak gösterilmektedir. Örnek oluşturma ve başlatma Masaüstü Uyarısı açılır penceresi de gösterir. Bu kod parçacığı parçasıdır [Masaüstü uyarı gösterim örneği](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DesktopAlertDemo#1](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwnd-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxDesktopAlertWnd.h

##  <a name="create"></a>  CMFCDesktopAlertWnd::Create

Oluşturur ve Masaüstü Uyarısı açılır penceresi başlatır.

```
virtual BOOL Create(
    CWnd* pWndOwner,
    UINT uiDlgResID,
    HMENU hMenu = NULL,
    CPoint ptPos = CPoint(-1,-1),
    CRuntimeClass* pRTIDlgBar = RUNTIME_CLASS(CMFCDesktopAlertDialog));

virtual BOOL Create(
    CWnd* pWndOwner,
    CMFCDesktopAlertWndInfo& params,
    HMENU hMenu = NULL,
    CPoint ptPos = CPoint(-1,-1));
```

### <a name="parameters"></a>Parametreler

*pWndOwner*<br/>
[out içinde] Uyarı pencerenin sahibini belirtir. Bu sahibi ardından Masaüstü Uyarısı açılır penceresi ilişkin tüm bildirimler alacaksınız. Bu değer NULL olamaz.

*uiDlgResID*<br/>
[in] Uyarı pencere kaynak Kimliğini belirtir.

*hMenu*<br/>
[in] Kullanıcı menü düğmesine tıkladığında görüntüler menüyü belirtir. NULL ise, menü düğmesine görüntülenmez.

*ptPos*<br/>
[in] Ekran koordinatları kullanarak, uyarı penceresi görüntüleyen ilk konumunu belirtir. Bu parametre ise (-1, -1) uyarı penceresi ekranının sağ alt köşesinde görüntülenir.

*pRTIDlgBar*<br/>
[in] Uyarı pencerenin istemci alanını kapsayan bir özel iletişim kutusu sınıfı için çalışma zamanı sınıf bilgileri.

*params*<br/>
[in] Bir uyarı pencere oluşturmak için kullanılan parametreleri belirtir.

### <a name="return-value"></a>Dönüş Değeri

Uyarı pencere başarıyla oluşturulursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bir uyarı pencere oluşturmak için bu yöntemi çağırın. Kullanıcıya görüntülenen tüm denetimleri barındıran alt iletişim kutusunda uyarı penceresinin istemci alanını içerir.

İlk yöntem aşırı yüklemesi, uygulamanın kaynaklardan yüklenen bir alt iletişim kutusu içeren bir uyarı pencere oluşturur. İlk yöntem aşırı yüklemesi, özel bir iletişim kutusu sınıfı için çalışma zamanı sınıf bilgileri de belirtebilirsiniz.

İkinci yöntem aşırı yükleme varsayılan denetim içeren bir uyarı pencere oluşturur. Değiştirerek görüntülenecek denetleyen belirtebilirsiniz [Cmfcdesktopalertwndınfo sınıfı](../../mfc/reference/cmfcdesktopalertwndinfo-class.md).

##  <a name="getanimationspeed"></a>  CMFCDesktopAlertWnd::GetAnimationSpeed

Animasyon hızı döndürür.

```
UINT GetAnimationSpeed() const;
```

### <a name="return-value"></a>Dönüş Değeri

Animasyon hızı uyarı penceresinin, milisaniye cinsinden.

### <a name="remarks"></a>Açıklamalar

Animasyon hızı ne kadar hızlı uyarı penceresi açılır ve kapatır açıklar.

##  <a name="getanimationtype"></a>  CMFCDesktopAlertWnd::GetAnimationType

Animasyon türü döndürür.

```
CMFCPopupMenu::ANIMATION_TYPE GetAnimationType();
```

### <a name="return-value"></a>Dönüş Değeri

Aşağıdaki animasyon türlerden biri:

- NO_ANIMATION

- DÜZLEŞTİRME

- SLAYT

- SOLUKLAŞTIR

- SYSTEM_DEFAULT_ANIMATION

##  <a name="getautoclosetime"></a>  CMFCDesktopAlertWnd::GetAutoCloseTime

Otomatik kapatma zaman aşımı döndürür.

```
int GetAutoCloseTime() const;
```

### <a name="return-value"></a>Dönüş Değeri

Milisaniye cinsinden süre geçmesi uyarı pencere otomatik olarak kapatılır.

### <a name="remarks"></a>Açıklamalar

Uyarı pencere otomatik olarak kapatılır önce ne kadar zaman geçmesi belirlemek için bu yöntemi kullanın.

##  <a name="getcaptionheight"></a>  CMFCDesktopAlertWnd::GetCaptionHeight

Açıklamalı alt yazı yüksekliğini döndürür.

```
virtual int GetCaptionHeight();
```

### <a name="return-value"></a>Dönüş Değeri

Açıklamalı alt yazı piksel cinsinden yüksekliği.

### <a name="remarks"></a>Açıklamalar

Bu yöntem türetilmiş bir sınıfta geçersiz kılınabilir. Varsayılan uygulama ya da: küçük resim yazısını veya Windows API işlevden alınan değer açılan pencere görüntülenmelidir küçük resim yazısı yükseklik değeri (7 piksel cinsinden) döndürür `GetSystemMetrics(SM_CYSMCAPTION)`.

##  <a name="getlastpos"></a>  CMFCDesktopAlertWnd::GetLastPos

Ekranda Masaüstü Uyarısı açılır penceresi son konumunu döndürür.

```
CPoint GetLastPos() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ekran koordinatlarında bir nokta.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ekranda uyarı penceresinin son geçerli konumunu döndürür.

##  <a name="gettransparency"></a>  CMFCDesktopAlertWnd::GetTransparency

Saydamlık düzeyini döndürür.

```
BYTE GetTransparency() const;
```

### <a name="return-value"></a>Dönüş Değeri

0 ve 255 arasında saydamlık düzeyi. Değer arttıkça, daha fazla opak penceresi.

### <a name="remarks"></a>Açıklamalar

Uyarı pencere geçerli saydamlık düzeyi almak için bu yöntemi kullanın.

##  <a name="hassmallcaption"></a>  CMFCDesktopAlertWnd::HasSmallCaption

Masaüstü Uyarısı açılır penceresi bir küçük resim yazısını veya normal boyut açıklama olup olmadığını belirler.

```
BOOL HasSmallCaption() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılan pencere bir küçük resim yazısı görüntüleniyorsa TRUE; Açılan pencere ile normal boyutlu bir başlık görüntüleniyorsa, FALSE.

### <a name="remarks"></a>Açıklamalar

Açılan pencere bir küçük resim yazısını veya normal boyut açıklama olup olmadığını belirlemek için bu yöntemi kullanın. Varsayılan olarak, küçük resim yazısı 7 piksel yüksekliğinde ' dir. Windows API işlevini çağırarak normal boyut açıklamalı alt yazı yüksekliğini edinebilirsiniz `GetSystemMetrics(SM_CYCAPTION)`.

##  <a name="onbeforeshow"></a>  CMFCDesktopAlertWnd::OnBeforeShow

```
virtual BOOL OnBeforeShow(CPoint&);
```

### <a name="parameters"></a>Parametreler

[in] *CPoint &*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="onclicklinkbutton"></a>  CMFCDesktopAlertWnd::OnClickLinkButton

Kullanıcının Masaüstü uyarı menüsünde bulunan bir bağlantı düğmesine tıkladığında framework tarafından çağırılır.

```
virtual BOOL OnClickLinkButton(UINT uiCmdID);
```

### <a name="parameters"></a>Parametreler

*uiCmdID*<br/>
[in] Bu parametre kullanılmaz.

### <a name="return-value"></a>Dönüş Değeri

Her zaman FALSE.

### <a name="remarks"></a>Açıklamalar

Bir kullanıcı, uyarı pencere bağlantısına tıkladığında bildirim almak istiyorsanız, türetilen bir sınıfta bu yöntemi yok sayın.

##  <a name="oncommand"></a>  CMFCDesktopAlertWnd::OnCommand

```
virtual BOOL OnCommand(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

[in] *wParam*<br/>

[in] *lParam*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="ondraw"></a>  CMFCDesktopAlertWnd::OnDraw

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

[in] *pDC*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="processcommand"></a>  CMFCDesktopAlertWnd::ProcessCommand

```
BOOL ProcessCommand(HWND hwnd);
```

### <a name="parameters"></a>Parametreler

[in] *hwnd*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="setanimationspeed"></a>  CMFCDesktopAlertWnd::SetAnimationSpeed

Yeni animasyon hızı ayarlar.

```
void SetAnimationSpeed(UINT nSpeed);
```

### <a name="parameters"></a>Parametreler

*nSpeed*<br/>
[in] Yeni animasyon hızı, milisaniye cinsinden belirtir.

### <a name="remarks"></a>Açıklamalar

Uyarı pencere için animasyon hızını ayarlamak için bu yöntemi çağırın. Varsayılan animasyon hızı 30 milisaniyedir.

##  <a name="setanimationtype"></a>  CMFCDesktopAlertWnd::SetAnimationType

Animasyon türünü ayarlar.

```
void SetAnimationType(CMFCPopupMenu::ANIMATION_TYPE type);
```

### <a name="parameters"></a>Parametreler

*type*<br/>
[in] Animasyon türü belirtir.

### <a name="remarks"></a>Açıklamalar

Animasyon türü ayarlamak için bu yöntemi çağırın. Aşağıdaki değerlerden birini belirleyebilirsiniz.

- NO_ANIMATION

- DÜZLEŞTİRME

- SLAYT

- SOLUKLAŞTIR

- SYSTEM_DEFAULT_ANIMATION

##  <a name="setautoclosetime"></a>  CMFCDesktopAlertWnd::SetAutoCloseTime

Otomatik kapatma zaman aşımı ayarlar.

```
void SetAutoCloseTime(int nTime);
```

### <a name="parameters"></a>Parametreler

*nZaman*<br/>
[in] Uyarı pencere otomatik olarak kapatılmadan önce milisaniye cinsinden süre, sona erdiğinde.

### <a name="remarks"></a>Açıklamalar

Kullanıcı pencere ile etkileşime girmez, uyarı penceresi belirtilen zamandan sonra otomatik olarak kapatılır.

##  <a name="setsmallcaption"></a>  CMFCDesktopAlertWnd::SetSmallCaption

Küçük ve normal boyut açıklamalı alt yazılar arasında geçiş yapar.

```
void SetSmallCaption(BOOL bSmallCaption = TRUE);
```

### <a name="parameters"></a>Parametreler

*bSmallCaption*<br/>
[in] Uyarı pencere bir küçük resim yazısı görüntüler belirtmek için TRUE; Aksi takdirde FALSE uyarı Pencereyi normal boyutuna açıklamalı alt yazı görüntüler belirtmek için.

### <a name="remarks"></a>Açıklamalar

Küçük veya normal boyut başlığı görüntülemek için bu yöntemi çağırın. Varsayılan olarak, küçük resim yazısı 7 piksel yüksekliğinde ' dir. Windows API işlevini çağırarak normal açıklamalı alt yazı boyutu edinebilirsiniz `GetSystemMetrics(SM_CYCAPTION)`.

##  <a name="settransparency"></a>  CMFCDesktopAlertWnd::SetTransparency

Açılan pencere saydamlık düzeyini ayarlar.

```
void SetTransparency(BYTE nTransparency);
```

### <a name="parameters"></a>Parametreler

*nTransparency*<br/>
[in] Saydamlık düzeyini belirtir. Bu değer, 0 ve 255, arasında olması gerekir. Değer arttıkça, daha fazla opak penceresi.

### <a name="remarks"></a>Açıklamalar

Açılan pencere saydamlık düzeyini ayarlamak için bu işlevi çağırın.

##  <a name="getdialogsize"></a>  CMFCDesktopAlertWnd::GetDialogSize

```
virtual CSize GetDialogSize();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertWndInfo Sınıfı](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)<br/>
[CMFCDesktopAlertDialog Sınıfı](../../mfc/reference/cmfcdesktopalertdialog-class.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)
