---
description: 'Daha fazla bilgi edinin: CMFCDesktopAlertWnd sınıfı'
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
ms.openlocfilehash: 45b75bdbd24a88a7eacff124bb07ac81e7703c31
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330093"
---
# <a name="cmfcdesktopalertwnd-class"></a>CMFCDesktopAlertWnd sınıfı

`CMFCDesktopAlertWnd`Sınıfı, kullanıcıya bir olay hakkında bilgilendirmek üzere ekranda görünen kalıcı olmayan bir iletişim kutusunun işlevselliğini uygular.

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Syntax

```
class CMFCDesktopAlertWnd : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCDesktopAlertWnd:: Create](#create)|Masaüstü Uyarısı penceresini oluşturur ve başlatır.|
|[CMFCDesktopAlertWnd:: GetAnimationSpeed](#getanimationspeed)|Animasyon hızını döndürür.|
|[CMFCDesktopAlertWnd:: GetAnimationType](#getanimationtype)|Animasyon türünü döndürür.|
|[CMFCDesktopAlertWnd:: GetAutoCloseTime](#getautoclosetime)|Otomatik kapatma zaman aşımını döndürür.|
|[CMFCDesktopAlertWnd:: GetCaptionHeight](#getcaptionheight)|Başlığın yüksekliğini döndürür.|
|[CMFCDesktopAlertWnd:: GetDialogSize](#getdialogsize)||
|[CMFCDesktopAlertWnd:: GetLastPos](#getlastpos)|Ekrandaki Masaüstü Uyarısı penceresinin son geçerli konumunu döndürür.|
|[CMFCDesktopAlertWnd:: GetTransparency](#gettransparency)|Saydamlık düzeyini döndürür.|
|[CMFCDesktopAlertWnd:: HasSmallCaption](#hassmallcaption)|Masaüstü Uyarısı penceresinin küçük açıklamalı alt başlıkla görüntülenip görüntülenmeyeceğini belirler.|
|[CMFCDesktopAlertWnd:: Onbeforesnasýl](#onbeforeshow)||
|[CMFCDesktopAlertWnd:: OnClickLinkButton](#onclicklinkbutton)|Kullanıcı Masaüstü Uyarısı menüsünde bulunan bir bağlantı düğmesine tıkladığında Framework tarafından çağırılır.|
|[CMFCDesktopAlertWnd:: OnCommand](#oncommand)|Bu üye işlevi, Kullanıcı menüden bir öğe seçtiğinde, alt denetim bir bildirim iletisi gönderdiğinde veya bir Hızlandırıcı tuş vuruşu çevrildiğinde Bu üye işlevini çağırır. ( [CWnd:: OnCommand](../../mfc/reference/cwnd-class.md#oncommand).) öğesini geçersiz kılar|
|[CMFCDesktopAlertWnd:: OnDraw](#ondraw)||
|[CMFCDesktopAlertWnd::P rocessCommand](#processcommand)||
|[CMFCDesktopAlertWnd:: SetAnimationSpeed](#setanimationspeed)|Yeni animasyon hızını ayarlar.|
|[CMFCDesktopAlertWnd:: SetAnimationType](#setanimationtype)|Animasyon türünü ayarlar.|
|[CMFCDesktopAlertWnd:: SetAutoCloseTime](#setautoclosetime)|Otomatik kapatma zaman aşımını ayarlar.|
|[CMFCDesktopAlertWnd:: SetSmallCaption](#setsmallcaption)|Küçük ve normal açıklamalı alt yazılar arasında geçiş yapar.|
|[CMFCDesktopAlertWnd:: Setasetatı](#settransparency)|Saydamlık düzeyini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bir masaüstü uyarısı penceresi saydam olabilir, animasyon efektleriyle görünebilir ve bu, belirli bir gecikmeden sonra veya Kullanıcı onu Kapat düğmesine tıklayarak yok edebilir.

Masaüstü Uyarısı penceresi ayrıca bir simge, ileti metni (etiket) ve bir bağlantı içeren bir varsayılan iletişim kutusu da içerebilir. Alternatif olarak, bir masaüstü uyarısı penceresi, uygulamanın kaynaklarından özel bir iletişim kutusu içerebilir.

İki adımda masaüstü uyarısı penceresi oluşturursunuz. İlk olarak, nesneyi oluşturmak için oluşturucuyu çağırın `CMFCDesktopAlertWnd` . İkinci olarak, pencereyi oluşturmak ve nesneye iliştirmek için [CMFCDesktopAlertWnd:: Create](#create) member işlevini çağırın `CMFCDesktopAlertWnd` .

`CMFCDesktopAlertWnd`Nesnesi, Masaüstü Uyarısı penceresinin istemci alanını dolduran özel bir alt iletişim kutusu oluşturur. İletişim kutusu, üzerine konumlandırılmış tüm denetimlere sahip olur.

Açılan pencerede özel bir iletişim kutusu göstermek için aşağıdaki adımları izleyin:

1. Sınıfından bir sınıf türet `CMFCDesktopAlertDialog` .

1. Kaynaklarda bir alt iletişim kutusu şablonu oluşturun.

1. İletişim kutusu şablonunun kaynak KIMLIĞINI ve türetilmiş sınıfın çalışma zamanı sınıf bilgilerine yönelik bir işaretçiyi kullanarak [CMFCDesktopAlertWnd:: Create](#create) ' i çağırın.

1. Barındırılan denetimlerden gelen tüm bildirimleri işlemek için özel iletişim kutusunu programlama veya barındırılan denetimleri bu bildirimleri doğrudan işleyecek şekilde programlama.

Masaüstü Uyarısı penceresinin davranışını denetlemek için aşağıdaki işlevleri kullanın:

- [CMFCDesktopAlertWnd:: SetAnimationType](#setanimationtype)öğesini çağırarak animasyon türünü ayarlayın. Geçerli seçenekler arasında katlama, kaydırma ve Soldur bulunur.

- [CMFCDesktopAlertWnd:: SetAnimationSpeed](#setanimationspeed)komutunu çağırarak animasyon çerçevesi hızını ayarlayın.

- [CMFCDesktopAlertWnd:: Setasetatı](#settransparency)çağırarak saydamlık düzeyini ayarlayın.

- [CMFCDesktopAlertWnd:: SetSmallCaption](#setsmallcaption)komutunu çağırarak başlık boyutunu küçük olarak değiştirin. Küçük Başlık 7 piksel yüksekliğinde.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCDesktopAlertWnd` bir nesneyi yapılandırmak için sınıfında çeşitli yöntemlerin nasıl kullanıldığını gösterir `CMFCDesktopAlertWnd` . Örnek, bir animasyon türü ayarlamayı, açılan pencerenin saydamlığını ayarlamayı gösterir, uyarı penceresinin küçük bir başlık görüntüleyeceğini belirtir ve uyarı penceresi otomatik olarak kapanmadan önce geçen süreyi ayarlar. Örnek ayrıca masaüstü uyarı penceresinin nasıl oluşturulduğunu ve başlatılacağını gösterir. Bu kod parçacığı, [Masaüstü Uyarısı tanıtım örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_DesktopAlertDemo#1](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwnd-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxDesktopAlertWnd. h

## <a name="cmfcdesktopalertwndcreate"></a><a name="create"></a> CMFCDesktopAlertWnd:: Create

Masaüstü Uyarısı penceresini oluşturur ve başlatır.

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
[in, out] Uyarı penceresinin sahibini belirtir. Bu sahip daha sonra Masaüstü Uyarısı penceresi için tüm bildirimleri alacaktır. Bu değer NULL olamaz.

*Uıdlgresd*<br/>
'ndaki Uyarı penceresinin kaynak KIMLIĞINI belirtir.

*hMenu*<br/>
'ndaki Kullanıcı menü düğmesine tıkladığında görüntülenen menüyü belirtir. NULL ise, menü düğmesi görüntülenmez.

*ptPos*<br/>
'ndaki Ekran koordinatları kullanılarak, uyarı penceresinin görüntülendiği başlangıç konumunu belirtir. Bu parametre (-1,-1) ise, uyarı penceresi ekranın sağ alt köşesinde görüntülenir.

*Prtidlbar çubuğu*<br/>
'ndaki Uyarı penceresinin istemci alanını içeren özel bir iletişim kutusu sınıfı için çalışma zamanı sınıfı bilgileri.

*params*<br/>
'ndaki Bir uyarı penceresi oluşturmak için kullanılan parametreleri belirtir.

### <a name="return-value"></a>Dönüş Değeri

Uyarı penceresi başarıyla oluşturulduysa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bir uyarı penceresi oluşturmak için bu yöntemi çağırın. Uyarı penceresinin istemci alanı, kullanıcıya görüntülenen tüm denetimleri barındıran bir alt iletişim kutusu içerir.

İlk yöntem aşırı yüklemesi, uygulamanın kaynaklarından yüklenen bir alt iletişim kutusu içeren bir uyarı penceresi oluşturur. İlk yöntem aşırı yüklemesi, özel bir iletişim kutusu sınıfı için çalışma zamanı sınıf bilgilerini de belirtebilir.

İkinci yöntem aşırı yüklemesi, varsayılan denetimleri içeren bir uyarı penceresi oluşturur. [Cmfcdesktopalertwnınfo sınıfını](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)değiştirerek hangi denetimlerin görüntüleneceğini belirtebilirsiniz.

## <a name="cmfcdesktopalertwndgetanimationspeed"></a><a name="getanimationspeed"></a> CMFCDesktopAlertWnd:: GetAnimationSpeed

Animasyon hızını döndürür.

```
UINT GetAnimationSpeed() const;
```

### <a name="return-value"></a>Dönüş Değeri

Uyarı penceresinin milisaniye cinsinden animasyon hızı.

### <a name="remarks"></a>Açıklamalar

Animasyon hızı, uyarı penceresinin ne kadar hızlı açıldığını ve kapanacağını açıklar.

## <a name="cmfcdesktopalertwndgetanimationtype"></a><a name="getanimationtype"></a> CMFCDesktopAlertWnd:: GetAnimationType

Animasyon türünü döndürür.

```
CMFCPopupMenu::ANIMATION_TYPE GetAnimationType();
```

### <a name="return-value"></a>Dönüş Değeri

Aşağıdaki animasyon türlerinden biri:

- NO_ANIMATION

- UNFOLD

- INıZA

- LARAK

- SYSTEM_DEFAULT_ANIMATION

## <a name="cmfcdesktopalertwndgetautoclosetime"></a><a name="getautoclosetime"></a> CMFCDesktopAlertWnd:: GetAutoCloseTime

Otomatik kapatma zaman aşımını döndürür.

```
int GetAutoCloseTime() const;
```

### <a name="return-value"></a>Dönüş Değeri

Uyarı penceresinin otomatik olarak kapanması için geçen süre (milisaniye cinsinden).

### <a name="remarks"></a>Açıklamalar

Uyarı penceresi otomatik olarak kapanmadan önce geçmesi gereken süreyi öğrenmek için bu yöntemi kullanın.

## <a name="cmfcdesktopalertwndgetcaptionheight"></a><a name="getcaptionheight"></a> CMFCDesktopAlertWnd:: GetCaptionHeight

Başlığın yüksekliğini döndürür.

```
virtual int GetCaptionHeight();
```

### <a name="return-value"></a>Dönüş Değeri

Başlığın piksel cinsinden yüksekliği.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, türetilmiş bir sınıfta geçersiz kılınabilir. Varsayılan uygulama: açılan pencere küçük resim yazısını veya Windows API işlevinden elde edilen değeri görüntülemesi gerekiyorsa, küçük resim yazısı yükseklik değerini (7 piksel) döndürür `GetSystemMetrics(SM_CYSMCAPTION)` .

## <a name="cmfcdesktopalertwndgetlastpos"></a><a name="getlastpos"></a> CMFCDesktopAlertWnd:: GetLastPos

Ekranda Masaüstü Uyarısı penceresinin son konumunu döndürür.

```
CPoint GetLastPos() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir nokta, Ekran koordinatlarında.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ekrandaki uyarı penceresinin son geçerli konumunu döndürür.

## <a name="cmfcdesktopalertwndgettransparency"></a><a name="gettransparency"></a> CMFCDesktopAlertWnd:: GetTransparency

Saydamlık düzeyini döndürür.

```
BYTE GetTransparency() const;
```

### <a name="return-value"></a>Dönüş Değeri

0 ile 255 (dahil) arasında bir saydamlık düzeyi. Değer arttıkça, pencere daha donuk olur.

### <a name="remarks"></a>Açıklamalar

Uyarı penceresinin geçerli saydamlık düzeyini almak için bu yöntemi kullanın.

## <a name="cmfcdesktopalertwndhassmallcaption"></a><a name="hassmallcaption"></a> CMFCDesktopAlertWnd:: HasSmallCaption

Masaüstü Uyarısı penceresinin küçük bir başlık veya normal boyut açıklamalı alt yazısını içerip içermediğini belirler.

```
BOOL HasSmallCaption() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılan pencere küçük bir başlık ile görüntüleniyorsa TRUE; Açılan pencere normal boyutlu bir başlık ile görüntüleniyorsa FALSE.

### <a name="remarks"></a>Açıklamalar

Açılan pencerenin küçük bir başlık veya normal boyutlu bir açıklamalı alt yazı içerip içermediğini anlamak için bu yöntemi kullanın. Varsayılan olarak, küçük Başlık 7 piksel yüksekliğinde. Windows API işlevini çağırarak normal boyut açıklamalı alt yazısının yüksekliğini elde edebilirsiniz `GetSystemMetrics(SM_CYCAPTION)` .

## <a name="cmfcdesktopalertwndonbeforeshow"></a><a name="onbeforeshow"></a> CMFCDesktopAlertWnd:: Onbeforesnasýl

```
virtual BOOL OnBeforeShow(CPoint&);
```

### <a name="parameters"></a>Parametreler

'ndaki *CPoint&*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdesktopalertwndonclicklinkbutton"></a><a name="onclicklinkbutton"></a> CMFCDesktopAlertWnd:: OnClickLinkButton

Kullanıcı Masaüstü Uyarısı menüsünde bulunan bir bağlantı düğmesine tıkladığında Framework tarafından çağırılır.

```
virtual BOOL OnClickLinkButton(UINT uiCmdID);
```

### <a name="parameters"></a>Parametreler

*Uıımıdıd*<br/>
'ndaki Bu parametre kullanılmaz.

### <a name="return-value"></a>Dönüş Değeri

Her zaman FALSE.

### <a name="remarks"></a>Açıklamalar

Bir Kullanıcı uyarı penceresindeki bağlantıya tıkladığında bildirim almak istiyorsanız, türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfcdesktopalertwndoncommand"></a><a name="oncommand"></a> CMFCDesktopAlertWnd:: OnCommand

```
virtual BOOL OnCommand(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

'ndaki *wParam*<br/>

'ndaki *lParam*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdesktopalertwndondraw"></a><a name="ondraw"></a> CMFCDesktopAlertWnd:: OnDraw

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

'ndaki *PDC*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdesktopalertwndprocesscommand"></a><a name="processcommand"></a> CMFCDesktopAlertWnd::P rocessCommand

```
BOOL ProcessCommand(HWND hwnd);
```

### <a name="parameters"></a>Parametreler

'ndaki *HWND*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdesktopalertwndsetanimationspeed"></a><a name="setanimationspeed"></a> CMFCDesktopAlertWnd:: SetAnimationSpeed

Yeni animasyon hızını ayarlar.

```cpp
void SetAnimationSpeed(UINT nSpeed);
```

### <a name="parameters"></a>Parametreler

*nSpeed*<br/>
'ndaki Yeni animasyon hızını milisaniye cinsinden belirtir.

### <a name="remarks"></a>Açıklamalar

Uyarı penceresinin animasyon hızını ayarlamak için bu yöntemi çağırın. Varsayılan animasyon hızı 30 milisaniyedir.

## <a name="cmfcdesktopalertwndsetanimationtype"></a><a name="setanimationtype"></a> CMFCDesktopAlertWnd:: SetAnimationType

Animasyon türünü ayarlar.

```cpp
void SetAnimationType(CMFCPopupMenu::ANIMATION_TYPE type);
```

### <a name="parameters"></a>Parametreler

*türüyle*<br/>
'ndaki Animasyon türünü belirtir.

### <a name="remarks"></a>Açıklamalar

Animasyon türünü ayarlamak için bu yöntemi çağırın. Aşağıdaki değerlerden birini belirleyebilirsiniz.

- NO_ANIMATION

- UNFOLD

- INıZA

- LARAK

- SYSTEM_DEFAULT_ANIMATION

## <a name="cmfcdesktopalertwndsetautoclosetime"></a><a name="setautoclosetime"></a> CMFCDesktopAlertWnd:: SetAutoCloseTime

Otomatik kapatma zaman aşımını ayarlar.

```cpp
void SetAutoCloseTime(int nTime);
```

### <a name="parameters"></a>Parametreler

*nZaman*<br/>
'ndaki Uyarı penceresi otomatik olarak kapanmadan önce geçen milisaniye cinsinden süre.

### <a name="remarks"></a>Açıklamalar

Kullanıcı pencereyle etkileşimde yoksa, uyarı penceresi belirtilen süreden sonra otomatik olarak kapatılır.

## <a name="cmfcdesktopalertwndsetsmallcaption"></a><a name="setsmallcaption"></a> CMFCDesktopAlertWnd:: SetSmallCaption

Küçük ve normal boyutlu açıklamalı alt yazılar arasında geçiş yapar.

```cpp
void SetSmallCaption(BOOL bSmallCaption = TRUE);
```

### <a name="parameters"></a>Parametreler

*bSmallCaption*<br/>
'ndaki Uyarı penceresinin küçük bir başlık görüntüleyeceğini belirtmek için TRUE; Aksi takdirde, uyarı penceresinin normal boyutlu bir başlık görüntüleyeceğini belirtmek için FALSE.

### <a name="remarks"></a>Açıklamalar

Küçük veya normal boyut başlığını göstermek için bu yöntemi çağırın. Varsayılan olarak, küçük Başlık 7 piksel yüksekliğinde. Windows API işlevini çağırarak normal başlık boyutunu elde edebilirsiniz `GetSystemMetrics(SM_CYCAPTION)` .

## <a name="cmfcdesktopalertwndsettransparency"></a><a name="settransparency"></a> CMFCDesktopAlertWnd:: Setasetatı

Açılan pencerenin saydamlık düzeyini ayarlar.

```cpp
void SetTransparency(BYTE nTransparency);
```

### <a name="parameters"></a>Parametreler

*nTransparency*<br/>
'ndaki Saydamlık düzeyini belirtir. Bu değer 0 ile 255 (dahil) arasında olmalıdır. Değer arttıkça, pencere daha donuk olur.

### <a name="remarks"></a>Açıklamalar

Açılan pencerenin saydamlık düzeyini ayarlamak için bu işlevi çağırın.

## <a name="cmfcdesktopalertwndgetdialogsize"></a><a name="getdialogsize"></a> CMFCDesktopAlertWnd:: GetDialogSize

```
virtual CSize GetDialogSize();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[Cmfcdesktopalertwnınfo sınıfı](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)<br/>
[CMFCDesktopAlertDialog sınıfı](../../mfc/reference/cmfcdesktopalertdialog-class.md)<br/>
[CWnd sınıfı](../../mfc/reference/cwnd-class.md)
