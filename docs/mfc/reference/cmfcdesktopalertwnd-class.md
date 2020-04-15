---
title: CMFCDesktopAlertWnd Sınıfı
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
ms.openlocfilehash: f9c59258cf757b5468985a954640ccec1543512b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367642"
---
# <a name="cmfcdesktopalertwnd-class"></a>CMFCDesktopAlertWnd Sınıfı

Sınıf, `CMFCDesktopAlertWnd` kullanıcıyı bir olay hakkında bilgilendirmek için ekranda görünen modeless iletişim kutusunun işlevselliğini uygular.

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Sözdizimi

```
class CMFCDesktopAlertWnd : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCDesktopAlertWnd::Oluştur](#create)|Masaüstü uyarı penceresini oluşturur ve başharfe ait hale leştirir.|
|[CMFCDesktopAlertWnd::GetAnimationSpeed](#getanimationspeed)|Animasyon hızını verir.|
|[CMFCDesktopAlertWnd::GetAnimationType](#getanimationtype)|Animasyon türünü döndürür.|
|[CMFCDesktopAlertWnd::GetAutoCloseTime](#getautoclosetime)|Otomatik kapatma saatini verir.|
|[CMFCDesktopAlertWnd::GetCaptionHeight](#getcaptionheight)|Başlığın yüksekliğini döndürür.|
|[CMFCDesktopAlertWnd::GetDialogSize](#getdialogsize)||
|[CMFCDesktopAlertWnd::GetLastPos](#getlastpos)|Ekrandaki masaüstü uyarı penceresinin son geçerli konumunu döndürür.|
|[CMFCDesktopAlertWnd::GetTransparency](#gettransparency)|Saydamlık düzeyini döndürür.|
|[CMFCDesktopAlertWnd::HasSmallCaption](#hassmallcaption)|Masaüstü uyarı penceresinin küçük resim yazısıyla görüntülenip görüntülenmediğini belirler.|
|[CMFCDesktopAlertWnd::OnBeforeShow](#onbeforeshow)||
|[CMFCDesktopAlertWnd::OnClickLinkButton](#onclicklinkbutton)|Kullanıcı masaüstü uyarı menüsünde bulunan bir bağlantı düğmesini tıklattığında çerçeve tarafından çağrılır.|
|[CMFCDesktopAlertWnd::OnCommand](#oncommand)|Çerçeve, kullanıcı menüden bir öğe seçtiğinde, alt denetim bir bildirim iletisi gönderdiğinde veya hızlandırıcı tuş vuruşu çevrildiğinde bu üye işlevi çağırır. (CWnd geçersiz [kılar::OnCommand](../../mfc/reference/cwnd-class.md#oncommand).)|
|[CMFCDesktopAlertWnd::OnDraw](#ondraw)||
|[CMFCDesktopAlertWnd::ProcessCommand](#processcommand)||
|[CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed)|Yeni animasyon hızını ayarlar.|
|[CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype)|Animasyon türünü ayarlar.|
|[CMFCDesktopAlertWnd::SetAutoCloseTime](#setautoclosetime)|Otomatik kapatma süresini ayarlar.|
|[CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption)|Küçük ve normal altyazılar arasında geçiş ler.|
|[CMFCDesktopAlertWnd::SetTransparency](#settransparency)|Saydamlık düzeyini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Masaüstü uyarı penceresi saydam olabilir, animasyon efektleriyle görünebilir ve kaybolabilir (belirli bir gecikmeden sonra veya kullanıcı kapat düğmesini tıklatarak kapatıldığında).

Masaüstü uyarı penceresi, sırayla bir simge, ileti metni (etiket) ve bir bağlantı içeren varsayılan bir iletişim kutusu da içerebilir. Alternatif olarak, masaüstü uyarı penceresi uygulamanın kaynaklarından özel bir iletişim kutusu içerebilir.

İki adımda bir masaüstü uyarı penceresi oluşturursunuz. İlk olarak, nesneyi oluşturmak `CMFCDesktopAlertWnd` için oluşturucuyu çağırın. İkinci olarak, [CMFCDesktopAlertWnd'i arayın::Pencereyi](#create) oluşturmak ve `CMFCDesktopAlertWnd` nesneye takmak için üye işlev oluşturun.

Nesne, `CMFCDesktopAlertWnd` masaüstü uyarı penceresinin istemci alanını dolduran özel bir alt iletişim kutusu oluşturur. İletişim kutusu, üzerinde konumlandırılmış tüm denetimlerin sahibidir.

Açılan pencerede özel bir iletişim kutusu görüntülemek için aşağıdaki adımları izleyin:

1. Bir sınıf türetmek `CMFCDesktopAlertDialog`.

1. Kaynaklarda bir alt iletişim kutusu şablonu oluşturun.

1. [CMFCDesktopAlertWnd'i arayın::İletişim](#create) kutusu şablonunun kaynak kimliğini ve türemiş sınıfın çalışma zamanı sınıf bilgilerine işaretçisini kullanarak oluşturun.

1. Barındırılan denetimlerden gelen tüm bildirimleri işlemek için özel iletişim kutusunu programlayın veya bu bildirimleri doğrudan işlemek için barındırılan denetimleri programlayın.

Masaüstü uyarı penceresinin davranışını denetlemek için aşağıdaki işlevleri kullanın:

- [CMFCDesktopAlertWnd::SetAnimationType'ı](#setanimationtype)arayarak animasyon türünü ayarlayın. Geçerli seçenekler açılma, slayt ve solukluk içerir.

- [CMFCDesktopAlertWnd::SetAnimationSpeed'i](#setanimationspeed)arayarak animasyon kare hızını ayarlayın.

- [CMFCDesktopAlertWnd'i](#settransparency)arayarak saydamlık düzeyini ayarlayın::SetTransparency .

- [CMFCDesktopAlertWnd::SetSmallCaption'ı](#setsmallcaption)arayarak resim yazısının boyutunu küçük olarak değiştirin. Küçük başlık 7 piksel yüksekliğindedir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CMFCDesktopAlertWnd` `CMFCDesktopAlertWnd` nesneyi yapılandırmak için sınıfta çeşitli yöntemlerin nasıl kullanılacağını göstermektedir. Örnek, animasyon türünü nasıl ayarladığını, açılır pencerenin saydamlık ını ayarladığını, uyarı penceresinin küçük bir resim yazısı gösterdiğini belirtmeyi ve uyarı penceresi otomatik olarak kapanmadan önce geçen süreyi ayarlamayı gösterir. Örnek, masaüstü uyarı penceresinin nasıl oluşturulup başharflerini de gösterir. Bu kod snippet [Masaüstü Uyarı Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_DesktopAlertDemo#1](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwnd-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxDesktopAlertWnd.h

## <a name="cmfcdesktopalertwndcreate"></a><a name="create"></a>CMFCDesktopAlertWnd::Oluştur

Masaüstü uyarı penceresini oluşturur ve başharfe ait hale leştirir.

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

*pWndSahibi*<br/>
[içinde, dışarı] Uyarı penceresinin sahibini belirtir. Bu sahip daha sonra masaüstü uyarı penceresi için tüm bildirimleri alır. Bu değer NULL olamaz.

*uiDlgResID*<br/>
[içinde] Uyarı penceresinin kaynak kimliğini belirtir.

*Hmenu*<br/>
[içinde] Kullanıcı menü düğmesini tıklattığında görüntüleyen menüyü belirtir. NULL ise menü düğmesi görüntülenmez.

*ptPos*<br/>
[içinde] Ekran koordinatlarını kullanarak uyarı penceresinin görüntülendiği ilk konumu belirtir. Bu parametre (-1, -1) ise, uyarı penceresi ekranın sağ alt köşesinde görüntülenir.

*pRTIDlgBar*<br/>
[içinde] Uyarı penceresinin istemci alanını kapsayan özel bir iletişim kutusu sınıfı için çalışma zamanı sınıf bilgileri.

*params*<br/>
[içinde] Uyarı penceresi oluşturmak için kullanılan parametreleri belirtir.

### <a name="return-value"></a>Dönüş Değeri

Uyarı penceresi başarıyla oluşturulduysa TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bir uyarı penceresi oluşturmak için bu yöntemi arayın. Uyarı penceresinin istemci alanı, kullanıcıya görüntülenen tüm denetimleri barındıran bir alt iletişim kutusu içerir.

İlk yöntem aşırı yükleme, uygulamanın kaynaklarından yüklenen bir alt iletişim kutusu içeren bir uyarı penceresi oluşturur. İlk yöntem aşırı yükleme, özel bir iletişim kutusu sınıfı için çalışma zamanı sınıf bilgilerini de belirtebilir.

İkinci yöntem aşırı yükleme varsayılan denetimleri içeren bir uyarı penceresi oluşturur. [CMFCDesktopAlertWndInfo Sınıfını](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)değiştirerek hangi denetimlerin görüntüleneceğini belirtebilirsiniz.

## <a name="cmfcdesktopalertwndgetanimationspeed"></a><a name="getanimationspeed"></a>CMFCDesktopAlertWnd::GetAnimationSpeed

Animasyon hızını verir.

```
UINT GetAnimationSpeed() const;
```

### <a name="return-value"></a>Dönüş Değeri

Uyarı penceresinin animasyon hızı, milisaniye cinsinden.

### <a name="remarks"></a>Açıklamalar

Animasyon hızı, uyarı penceresinin ne kadar hızlı açılıp kapandığını açıklar.

## <a name="cmfcdesktopalertwndgetanimationtype"></a><a name="getanimationtype"></a>CMFCDesktopAlertWnd::GetAnimationType

Animasyon türünü döndürür.

```
CMFCPopupMenu::ANIMATION_TYPE GetAnimationType();
```

### <a name="return-value"></a>Dönüş Değeri

Aşağıdaki animasyon türlerinden biri:

- NO_ANIMATION

- Açılmak

- Slayt

- Fade

- SYSTEM_DEFAULT_ANIMATION

## <a name="cmfcdesktopalertwndgetautoclosetime"></a><a name="getautoclosetime"></a>CMFCDesktopAlertWnd::GetAutoCloseTime

Otomatik kapatma saatini verir.

```
int GetAutoCloseTime() const;
```

### <a name="return-value"></a>Dönüş Değeri

Saat, milisaniye cinsinden, ardından uyarı penceresi otomatik olarak kapanır.

### <a name="remarks"></a>Açıklamalar

Uyarı penceresi otomatik olarak kapanmadan önce ne kadar zaman geçmesi gerektiğini belirlemek için bu yöntemi kullanın.

## <a name="cmfcdesktopalertwndgetcaptionheight"></a><a name="getcaptionheight"></a>CMFCDesktopAlertWnd::GetCaptionHeight

Başlığın yüksekliğini döndürür.

```
virtual int GetCaptionHeight();
```

### <a name="return-value"></a>Dönüş Değeri

Başlık yüksekliği, piksel olarak, başlık.

### <a name="remarks"></a>Açıklamalar

Bu yöntem türetilmiş bir sınıfta geçersiz kılınabilir. Varsayılan uygulama ya: açılır pencere küçük başlık veya Windows API işlevinden `GetSystemMetrics(SM_CYSMCAPTION)`elde edilen değeri görüntülemek gerekiyorsa küçük resim yazısı yüksekliği değeri (7 piksel) döndürür.

## <a name="cmfcdesktopalertwndgetlastpos"></a><a name="getlastpos"></a>CMFCDesktopAlertWnd::GetLastPos

Ekrandaki masaüstü uyarı penceresinin son konumunu döndürür.

```
CPoint GetLastPos() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir nokta, ekran koordinatlarında.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ekrandaki uyarı penceresinin son geçerli konumunu döndürür.

## <a name="cmfcdesktopalertwndgettransparency"></a><a name="gettransparency"></a>CMFCDesktopAlertWnd::GetTransparency

Saydamlık düzeyini döndürür.

```
BYTE GetTransparency() const;
```

### <a name="return-value"></a>Dönüş Değeri

0 ile 255 arasında bir şeffaflık düzeyi, dahil. Değer ne kadar büyükse, pencere okadar opak.

### <a name="remarks"></a>Açıklamalar

Uyarı penceresinin geçerli saydamlık düzeyini almak için bu yöntemi kullanın.

## <a name="cmfcdesktopalertwndhassmallcaption"></a><a name="hassmallcaption"></a>CMFCDesktopAlertWnd::HasSmallCaption

Masaüstü uyarı penceresinin küçük bir resim yazısı mı yoksa normal boyutlu bir resim yazısı mı olduğunu belirler.

```
BOOL HasSmallCaption() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılır pencere küçük bir başlıkla görüntülenirse DOĞRU; Açılır pencere normal boyutlu bir başlıkla görüntülenirse YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Açılır pencerenin küçük bir resim yazısı mı yoksa normal boyutlu bir resim yazısı mı olduğunu belirlemek için bu yöntemi kullanın. Varsayılan olarak, küçük başlık 7 piksel yüksekliğindedir. Windows API işlevini `GetSystemMetrics(SM_CYCAPTION)`arayarak normal boyut alt yazısının yüksekliğini elde edebilirsiniz.

## <a name="cmfcdesktopalertwndonbeforeshow"></a><a name="onbeforeshow"></a>CMFCDesktopAlertWnd::OnBeforeShow

```
virtual BOOL OnBeforeShow(CPoint&);
```

### <a name="parameters"></a>Parametreler

[içinde] *CPoint&*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdesktopalertwndonclicklinkbutton"></a><a name="onclicklinkbutton"></a>CMFCDesktopAlertWnd::OnClickLinkButton

Kullanıcı masaüstü uyarı menüsünde bulunan bir bağlantı düğmesini tıklattığında çerçeve tarafından çağrılır.

```
virtual BOOL OnClickLinkButton(UINT uiCmdID);
```

### <a name="parameters"></a>Parametreler

*uiCmdID*<br/>
[içinde] Bu parametre kullanılmaz.

### <a name="return-value"></a>Dönüş Değeri

Her zaman FALSE.

### <a name="remarks"></a>Açıklamalar

Kullanıcı uyarı penceresindeki bağlantıyı tıklattığında bilgilendirilmek istiyorsanız, türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfcdesktopalertwndoncommand"></a><a name="oncommand"></a>CMFCDesktopAlertWnd::OnCommand

```
virtual BOOL OnCommand(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

[içinde] *wParam*<br/>

[içinde] *lParam*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdesktopalertwndondraw"></a><a name="ondraw"></a>CMFCDesktopAlertWnd::OnDraw

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

[içinde] *pDC*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdesktopalertwndprocesscommand"></a><a name="processcommand"></a>CMFCDesktopAlertWnd::ProcessCommand

```
BOOL ProcessCommand(HWND hwnd);
```

### <a name="parameters"></a>Parametreler

[içinde] *hwnd*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdesktopalertwndsetanimationspeed"></a><a name="setanimationspeed"></a>CMFCDesktopAlertWnd::SetAnimationSpeed

Yeni animasyon hızını ayarlar.

```
void SetAnimationSpeed(UINT nSpeed);
```

### <a name="parameters"></a>Parametreler

*nHız*<br/>
[içinde] Yeni animasyon hızını milisaniye cinsinden belirtir.

### <a name="remarks"></a>Açıklamalar

Uyarı penceresinin animasyon hızını ayarlamak için bu yöntemi arayın. Varsayılan animasyon hızı 30 milisaniyedir.

## <a name="cmfcdesktopalertwndsetanimationtype"></a><a name="setanimationtype"></a>CMFCDesktopAlertWnd::SetAnimationType

Animasyon türünü ayarlar.

```
void SetAnimationType(CMFCPopupMenu::ANIMATION_TYPE type);
```

### <a name="parameters"></a>Parametreler

*Türü*<br/>
[içinde] Animasyon türünü belirtir.

### <a name="remarks"></a>Açıklamalar

Animasyon türünü ayarlamak için bu yöntemi arayın. Aşağıdaki değerlerden birini belirleyebilirsiniz.

- NO_ANIMATION

- Açılmak

- Slayt

- Fade

- SYSTEM_DEFAULT_ANIMATION

## <a name="cmfcdesktopalertwndsetautoclosetime"></a><a name="setautoclosetime"></a>CMFCDesktopAlertWnd::SetAutoCloseTime

Otomatik kapatma süresini ayarlar.

```
void SetAutoCloseTime(int nTime);
```

### <a name="parameters"></a>Parametreler

*nZaman*<br/>
[içinde] Uyarı penceresi otomatik olarak kapanmadan önce zaman, milisaniye cinsinden, bu kadar sürer.

### <a name="remarks"></a>Açıklamalar

Kullanıcı pencereyle etkileşimde değilse, uyarı penceresi belirtilen süreden sonra otomatik olarak kapatılır.

## <a name="cmfcdesktopalertwndsetsmallcaption"></a><a name="setsmallcaption"></a>CMFCDesktopAlertWnd::SetSmallCaption

Küçük ve normal boyutlu altyazılar arasında geçiş ler.

```
void SetSmallCaption(BOOL bSmallCaption = TRUE);
```

### <a name="parameters"></a>Parametreler

*bSmallCaption*<br/>
[içinde] Uyarı penceresinin küçük bir resim yazısı görüntülediğini belirtmek için TRUE; aksi takdirde, uyarı penceresinin normal boyutta bir resim yazısı görüntülediğini belirtmek için FALSE.

### <a name="remarks"></a>Açıklamalar

Küçük veya normal boyutlu alt yazıyı görüntülemek için bu yöntemi arayın. Varsayılan olarak, küçük başlık 7 piksel yüksekliğindedir. Windows API işlevini `GetSystemMetrics(SM_CYCAPTION)`arayarak normal altyazıboyutunu elde edebilirsiniz.

## <a name="cmfcdesktopalertwndsettransparency"></a><a name="settransparency"></a>CMFCDesktopAlertWnd::SetTransparency

Açılır pencerenin saydamlık düzeyini ayarlar.

```
void SetTransparency(BYTE nTransparency);
```

### <a name="parameters"></a>Parametreler

*nŞeffaflık*<br/>
[içinde] Saydamlık düzeyini belirtir. Bu değer 0 ile 255 arasında, dahil olmalıdır. Değer ne kadar büyükse, pencere okadar opak.

### <a name="remarks"></a>Açıklamalar

Açılır pencerenin saydamlık düzeyini ayarlamak için bu işlevi çağırın.

## <a name="cmfcdesktopalertwndgetdialogsize"></a><a name="getdialogsize"></a>CMFCDesktopAlertWnd::GetDialogSize

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
