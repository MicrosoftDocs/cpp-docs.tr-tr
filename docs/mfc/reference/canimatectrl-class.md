---
title: CAnimateCtrl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAnimateCtrl
- AFXCMN/CAnimateCtrl
- AFXCMN/CAnimateCtrl::CAnimateCtrl
- AFXCMN/CAnimateCtrl::Close
- AFXCMN/CAnimateCtrl::Create
- AFXCMN/CAnimateCtrl::CreateEx
- AFXCMN/CAnimateCtrl::IsPlaying
- AFXCMN/CAnimateCtrl::Open
- AFXCMN/CAnimateCtrl::Play
- AFXCMN/CAnimateCtrl::Seek
- AFXCMN/CAnimateCtrl::Stop
helpviewer_keywords:
- CAnimateCtrl [MFC], CAnimateCtrl
- CAnimateCtrl [MFC], Close
- CAnimateCtrl [MFC], Create
- CAnimateCtrl [MFC], CreateEx
- CAnimateCtrl [MFC], IsPlaying
- CAnimateCtrl [MFC], Open
- CAnimateCtrl [MFC], Play
- CAnimateCtrl [MFC], Seek
- CAnimateCtrl [MFC], Stop
ms.assetid: 5e8eb1bd-96b7-47b8-8de2-6bcbb3cc299b
ms.openlocfilehash: fcee569659d732c26e274c8ca189042a16f13557
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371061"
---
# <a name="canimatectrl-class"></a>CAnimateCtrl Sınıfı

Windows ortak animasyon denetiminin işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CAnimateCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAnimateCtrl::CAnimateCtrl](#canimatectrl)|Bir `CAnimateCtrl` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimateCtrl::Kapat](#close)|AVI klibini kapatır.|
|[CAnimateCtrl::Oluştur](#create)|Animasyon denetimi oluşturur ve nesneye `CAnimateCtrl` bağlar.|
|[CAnimateCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleri ile bir animasyon denetimi oluşturur `CAnimateCtrl` ve bir nesneye bağlar.|
|[CAnimateCtrl::Yürütülüyor](#isplaying)|Sesli-Video Ara (AVI) klibinin oynatılıp oynanmadığını gösterir.|
|[CAnimateCtrl::Aç](#open)|Bir dosyaveya kaynaktan avi klibini açar ve ilk kareyi görüntüler.|
|[CAnimateCtrl::Play](#play)|AVI klibini ses olmadan çalar.|
|[CAnimateCtrl::Ara](#seek)|AVI klibinin seçili tek bir karesini görüntüler.|
|[CAnimateCtrl::Dur](#stop)|AVI klibini çalmayı durdurur.|

## <a name="remarks"></a>Açıklamalar

Bu denetim (ve `CAnimateCtrl` bu nedenle sınıf) yalnızca Windows 95, Windows 98 ve Windows NT sürüm 3.51 ve sonraki sürümler altında çalışan programlar için kullanılabilir.

Animasyon denetimi, standart Windows video/ses biçimi olan AVI (Audio Video Interleaved) biçiminde bir klibi görüntüleyen dikdörtgen bir penceredir. AVI klibi, film gibi bir dizi bitmap çerçevesidir.

Animasyon denetimleri yalnızca basit AVI klipleri oynatabilir. Özellikle, animasyon denetimi tarafından oynan klipler aşağıdaki gereksinimleri karşılamalıdır:

- Tam olarak bir video akışı olmalı ve en az bir kare olmalıdır.

- Dosyada en fazla iki akış olabilir (animasyon denetimi ses bilgilerini yok saysa da, genellikle diğer akış, varsa bir ses akışıdır).

- Klip, RLE8 sıkıştırma ile sıkıştırılmamış veya sıkıştırılmış olmalıdır.

- Video akışında palet değişikliğine izin verilmez.

AVI klibini uygulamanıza AVI kaynağı olarak ekleyebilirsiniz veya ayrı bir AVI dosyası olarak başvurunuza eşlik edebilir.

AVI klibi görüntülenirken iş parçacığınız yürütmeye devam ettiği için, animasyon denetimiiçin yaygın olarak kullanılan kullanımlardan biri, uzun bir işlem sırasında sistem etkinliğini belirtmektir. Örneğin, Dosya Gezgini'nin Bul iletişim kutusu, sistem bir dosyayı ararken hareketli bir büyüteç görüntüler.

İletişim düzenleyicisini `CAnimateCtrl` kullanarak iletişim kutusu içinde veya iletişim kaynağından bir nesne oluşturursanız, kullanıcı iletişim kutusunu kapattığında nesne otomatik olarak yok olur.

Bir pencere `CAnimateCtrl` içinde bir nesne oluşturursanız, onu yok etmek gerekebilir. Yığının `CAnimateCtrl` üzerinde nesne oluşturursanız, otomatik olarak yok edilir. Nesneyi `CAnimateCtrl` **yeni** işlevi kullanarak yığında oluşturursanız, nesneyi yok etmek için nesneye **sil** çağrısında bulunuyorsunuz. Bu sınıftan `CAnimateCtrl` yeni bir sınıf türetin ve bu sınıftaki herhangi bir belleği ayırın, ayırmaları elden çıkarmak için yıkıcıyı `CAnimateCtrl` geçersiz kılın.

Kullanma `CAnimateCtrl`hakkında daha fazla bilgi [Using CAnimateCtrl](../../mfc/using-canimatectrl.md)için, [bkz.](../../mfc/controls-mfc.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CAnimateCtrl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

## <a name="canimatectrlcanimatectrl"></a><a name="canimatectrl"></a>CAnimateCtrl::CAnimateCtrl

Bir `CAnimateCtrl` nesne inşa eder.

```
CAnimateCtrl();
```

### <a name="remarks"></a>Açıklamalar

Oluşturduğunuz nesne üzerinde başka işlemler gerçekleştiremeden önce [Üye Oluştur](#create) işlevini aramanız gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#56](../../mfc/codesnippet/cpp/canimatectrl-class_1.cpp)]

## <a name="canimatectrlclose"></a><a name="close"></a>CAnimateCtrl::Kapat

Animasyon denetiminde daha önce açılmış olan AVI klibini kapatır (varsa) ve bellekten kaldırır.

```
BOOL Close();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="example"></a>Örnek

  [CAnimateCtrl::CAnimateCtrl](#canimatectrl)için örneğe bakın.

## <a name="canimatectrlcreate"></a><a name="create"></a>CAnimateCtrl::Oluştur

Animasyon denetimi oluşturur ve nesneye `CAnimateCtrl` bağlar.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
Animasyon denetiminin stilini belirtir. Aşağıdaki Açıklamalar bölümünde açıklanan windows stilleri ile Windows SDK'da [Animasyon Denetim Stilleri'nde](/windows/win32/Controls/animation-control-styles) açıklanan animasyon denetim stillerinin herhangi bir birleşimini uygulayın.

*Rect*<br/>
Animasyon denetiminin konumunu ve boyutunu belirtir. Bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya [RECT](/windows/win32/api/windef/ns-windef-rect) yapısı olabilir.

*pParentWnd*<br/>
Animasyon denetiminin üst penceresini belirtir, `CDialog`genellikle bir . NULL olmamalıdır.

*Nıd*<br/>
Animasyon denetiminin kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

İki adımda bir `CAnimateCtrl` yapı inşa e. Önce oluşturucuyu çağırın, `Create`sonra animasyon denetimini oluşturan ve `CAnimateCtrl` nesneye iliştiren , çağırın.

Aşağıdaki [pencere stillerini](../../mfc/reference/styles-used-by-mfc.md#window-styles) animasyon denetimine uygulayın.

- WS_CHILD Her Zaman

- WS_VISIBLE Genellikle

- WS_DISABLED Nadiren

Animasyon denetiminiz ile genişletilmiş pencere stillerini kullanmak istiyorsanız, `Create`'' yerine [CreateEx'i](#createex) arayın.

Yukarıda listelenen pencere stillerine ek olarak, animasyon denetim stillerinden birini veya birkaçını animasyon denetimine uygulamak isteyebilirsiniz. [Animasyon denetim stilleri](/windows/win32/Controls/animation-control-styles)hakkında daha fazla bilgi için Windows SDK'ya bakın.

### <a name="example"></a>Örnek

  [CAnimateCtrl::CAnimateCtrl](#canimatectrl)için örneğe bakın.

## <a name="canimatectrlcreateex"></a><a name="createex"></a>CAnimateCtrl::CreateEx

Denetim (alt pencere) oluşturur ve `CAnimateCtrl` nesneyle ilişkilendirir.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwExStyle*<br/>
Oluşturulan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stillerilistesi için Windows SDK'daki [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) için *dwExStyle* parametreye bakın.

*Dwstyle*<br/>
Animasyon denetiminin stilini belirtir. Windows SDK'da [Animasyon Denetim Stilleri'nde](/windows/win32/Controls/animation-control-styles) açıklanan pencere ve animasyon denetim stillerinin herhangi bir birleşimini uygulayın.

*Rect*<br/>
*PParentWnd*istemci koordinatlarında oluşturulacak pencerenin boyutunu ve konumunu açıklayan bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısına başvuru.

*pParentWnd*<br/>
Denetimin üst öğesi olan pencereye işaretçi.

*Nıd*<br/>
Denetimin alt pencere kimliği.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Windows `CreateEx` genişletilmiş stil önsöz **WS_EX_** tarafından belirtilen genişletilmiş Windows stilleri uygulamak için [Oluştur](#create) yerine kullanın.

## <a name="canimatectrlisplaying"></a><a name="isplaying"></a>CAnimateCtrl::Yürütülüyor

Sesli-Video Ara (AVI) klibinin oynatılıp oynanmadığını gösterir.

```
BOOL IsPlaying() const;
```

### <a name="return-value"></a>Dönüş Değeri

BIR AVI klibi oynatılırsa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [ACM_ISPLAYING](/windows/win32/Controls/acm-isplaying) iletisini gönderir.

## <a name="canimatectrlopen"></a><a name="open"></a>CAnimateCtrl::Aç

Avi klibini açmak ve ilk karesini görüntülemek için bu işlevi arayın.

```
BOOL Open(LPCTSTR lpszFileName);
BOOL Open(UINT nID);
```

### <a name="parameters"></a>Parametreler

*lpszFileName*<br/>
Avi `CString` dosyasının adını veya AVI kaynağının adını içeren geçersiz sonlandırılmış bir dize için bir nesne veya işaretçi. Bu parametre NULL ise, sistem varsa, animasyon denetimi için daha önce açılmış olan AVI klibini kapatır.

*Nıd*<br/>
AVI kaynak tanımlayıcısı. Bu parametre NULL ise, sistem varsa, animasyon denetimi için daha önce açılmış olan AVI klibini kapatır.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

AVI kaynağı animasyon denetimini oluşturan modülden yüklenir.

`Open`AVI klibindeki sesi desteklemez; yalnızca sessiz AVI klipleri açabilirsiniz.

Animasyon denetimi `ACS_AUTOPLAY` nde stil varsa, animasyon denetimi klibi açtıktan hemen sonra otomatik olarak oynatmaya başlar. İş parçacığınız çalışmaya devam ederken klibi arka planda oynatmaya devam edecektir. Klip oynatılmalı yapıldığında, otomatik olarak tekrarlanır.

Animasyon denetimi `ACS_CENTER` nin stili varsa, AVI klibi denetimde ortalanır ve denetimin boyutu değişmez. Animasyon `ACS_CENTER` denetiminde stil yoksa, AVI klibi AVI klibindeki görüntülerin boyutuna açıldığında denetim yeniden boyutlandırılır. Denetimin sol üst köşesindeki konumu değişmez, yalnızca denetimin boyutu değişir.

Animasyon denetimi stiline `ACS_TRANSPARENT` sahipse, ilk kare animasyon klibinde belirtilen arka plan rengi yerine saydam bir arka plan kullanılarak çizilir.

### <a name="example"></a>Örnek

  [CAnimateCtrl::CAnimateCtrl](#canimatectrl)için örneğe bakın.

## <a name="canimatectrlplay"></a><a name="play"></a>CAnimateCtrl::Play

Animasyon denetiminde avi klibini oynatmak için bu işlevi arayın.

```
BOOL Play(
    UINT nFrom,
    UINT nTo,
    UINT nRep);
```

### <a name="parameters"></a>Parametreler

*nKaynak*<br/>
Çalmanın başladığı çerçevenin sıfır tabanlı dizini. Değeri 65.536'dan az olmalıdır. 0 değeri, AVI klibindeki ilk kareyle başlar anlamına gelir.

*nTo*<br/>
Oynatmanın sona erdiği çerçevenin sıfır tabanlı dizini. Değeri 65.536'dan az olmalıdır. - 1 değeri, AVI klibindeki son kareyle sona erdirme anlamına gelir.

*nRep*<br/>
AVI klibini tekrar oynatma sayısı. - 1 değeri, dosyayı süresiz olarak yeniden oynatmak anlamına gelir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

İş parçacığınız yürütmeye devam ederken animasyon denetimi klibi arka planda yürütür. Animasyon denetiminin `ACS_TRANSPARENT` stili varsa, AVI klibi animasyon klibinde belirtilen arka plan rengi yerine saydam bir arka plan kullanılarak oynatılacaktır.

### <a name="example"></a>Örnek

  [CAnimateCtrl::CAnimateCtrl](#canimatectrl)için örneğe bakın.

## <a name="canimatectrlseek"></a><a name="seek"></a>CAnimateCtrl::Ara

AVI klibinizin tek bir karesini statik olarak görüntülemek için bu işlevi arayın.

```
BOOL Seek(UINT nTo);
```

### <a name="parameters"></a>Parametreler

*nTo*<br/>
Görüntülenecek çerçevenin sıfır tabanlı dizin. Değeri 65.536'dan az olmalıdır. 0 değeri, AVI klibindeki ilk kareyi görüntülemek anlamına gelir. -1 değeri, SON kareyi AVI klibinde görüntülemek anlamına gelir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

Animasyon denetiminin `ACS_TRANSPARENT` stili varsa, AVI klibi animasyon klibinde belirtilen arka plan rengi yerine saydam bir arka plan kullanılarak çizilir.

### <a name="example"></a>Örnek

[CAnimateCtrl::CAnimateCtrl](#canimatectrl)için örneğe bakın.

## <a name="canimatectrlstop"></a><a name="stop"></a>CAnimateCtrl::Dur

Animasyon denetiminde AVI klibini oynatmayı durdurmak için bu işlevi arayın.

```
BOOL Stop();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="example"></a>Örnek

  [CAnimateCtrl::CAnimateCtrl](#canimatectrl)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CAnimateCtrl::Oluştur](#create)<br/>
[ON_CONTROL](message-map-macros-mfc.md#on_control)
