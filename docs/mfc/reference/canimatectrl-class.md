---
description: 'Daha fazla bilgi edinin: CAnimateCtrl sınıfı'
title: CAnimateCtrl sınıfı
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
ms.openlocfilehash: fe63e30ae53e6f5b3d308c8e09f0bfbaad76b2ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322752"
---
# <a name="canimatectrl-class"></a>CAnimateCtrl sınıfı

Windows ortak animasyon denetimi işlevlerini sağlar.

## <a name="syntax"></a>Syntax

```
class CAnimateCtrl : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAnimateCtrl:: CAnimateCtrl](#canimatectrl)|Bir `CAnimateCtrl` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimateCtrl:: Close](#close)|AVI klibini kapatır.|
|[CAnimateCtrl:: Create](#create)|Bir animasyon denetimi oluşturur ve bunu bir nesneye ekler `CAnimateCtrl` .|
|[CAnimateCtrl:: CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleriyle bir animasyon denetimi oluşturur ve bunu bir `CAnimateCtrl` nesneye ekler.|
|[CAnimateCtrl:: ısçalıyor](#isplaying)|Audio-Video Aralanmış (AVI) klibinin çalıp oynatılmadığını gösterir.|
|[CAnimateCtrl:: Open](#open)|Bir dosya veya kaynaktan bir AVI klibi açar ve ilk çerçeveyi görüntüler.|
|[CAnimateCtrl::P Lay](#play)|AVI klibini ses olmadan çalar.|
|[CAnimateCtrl:: Seek](#seek)|AVI klibinin seçili tek bir çerçevesini görüntüler.|
|[CAnimateCtrl:: stop](#stop)|AVI klibini çalmayı durduruyor.|

## <a name="remarks"></a>Açıklamalar

Bu denetim (ve bu nedenle `CAnimateCtrl` sınıfı) yalnızca windows 95, windows 98 ve WINDOWS NT sürüm 3,51 ve üzeri sürümlerde çalışan programlar için kullanılabilir.

Animasyon denetimi, standart Windows video/ses biçimi olan avı (ses video Aralanmış) biçiminde bir klip görüntüleyen dikdörtgen bir penceredir. AVI klibi, film gibi bir bit eşlem çerçevesi dizisidir.

Animasyon denetimleri yalnızca basit AVI klipleri oynayabilir. Özellikle, bir animasyon denetimi tarafından çalınan kliplerin aşağıdaki gereksinimleri karşılaması gerekir:

- Tam olarak bir video akışı olmalıdır ve en az bir çerçevesine sahip olmalıdır.

- Dosyada en fazla iki akış bulunabilir (genellikle, varsa diğer akış bir ses akışıdır, ancak animasyon denetimi ses bilgilerini yoksayar).

- Klip, RLE8 Compression ile sıkıştırılmamış veya sıkıştırılmış olmalıdır.

- Video akışında palet değişikliğine izin verilmez.

AVI klibini uygulamanıza bir avı kaynağı olarak ekleyebilir ya da uygulamanıza ayrı bir AVI dosyası olarak eşlik edebilir.

AVI klibi görüntülenirken iş parçacığın yürütmeye devam ettiğinden, bir animasyon denetimi için yaygın olarak kullanılan bir kullanım, uzun bir işlem sırasında sistem etkinliğini gösterir. Örneğin, dosya Gezgini 'nin bul iletişim kutusu, bir dosya için sistem ararken bir hareketli Büyüteç Camı görüntüler.

İletişim `CAnimateCtrl` kutusu içinde veya iletişim kutusu düzenleyicisini kullanarak bir iletişim kutusu kaynağından bir nesne oluşturursanız, Kullanıcı iletişim kutusunu kapattığında otomatik olarak yok edilir.

Bir `CAnimateCtrl` pencere içinde bir nesne oluşturursanız, bunu yok etmeniz gerekebilir. `CAnimateCtrl`Nesneyi yığında oluşturursanız, otomatik olarak yok edilir. `CAnimateCtrl`Nesnesini, işlevini kullanarak yığında oluşturursanız **`new`** , **`delete`** nesneyi yok etmek için çağırmak zorundasınız. ' Dan yeni bir sınıf türetirsiniz `CAnimateCtrl` ve bu sınıftaki herhangi bir bellek ayırdıysanız, `CAnimateCtrl` ayırmaları atmak için yıkıcıyı geçersiz kılın.

Kullanma hakkında daha fazla bilgi için `CAnimateCtrl` bkz. [Controls](../../mfc/controls-mfc.md) ve [CAnimateCtrl kullanma](../../mfc/using-canimatectrl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CAnimateCtrl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcmn. h

## <a name="canimatectrlcanimatectrl"></a><a name="canimatectrl"></a> CAnimateCtrl:: CAnimateCtrl

Bir `CAnimateCtrl` nesnesi oluşturur.

```
CAnimateCtrl();
```

### <a name="remarks"></a>Açıklamalar

Oluşturduğunuz nesnede başka bir işlem gerçekleştirebilmek için önce [Create](#create) member işlevini çağırmanız gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#56](../../mfc/codesnippet/cpp/canimatectrl-class_1.cpp)]

## <a name="canimatectrlclose"></a><a name="close"></a> CAnimateCtrl:: Close

Daha önce animasyon denetiminde açılan olan avı klibini (varsa) kapatır ve bellekten kaldırır.

```
BOOL Close();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="example"></a>Örnek

  [CAnimateCtrl:: CAnimateCtrl](#canimatectrl)örneğine bakın.

## <a name="canimatectrlcreate"></a><a name="create"></a> CAnimateCtrl:: Create

Bir animasyon denetimi oluşturur ve bunu bir nesneye ekler `CAnimateCtrl` .

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Animasyon denetiminin stilini belirtir. Aşağıdaki açıklamalar bölümünde açıklanan Windows stillerinin ve Windows SDK [animasyon denetim stillerinde](/windows/win32/Controls/animation-control-styles) açıklanan animasyon denetim stillerinin birleşimini uygulayın.

*Rect*<br/>
Animasyon denetiminin konumunu ve boyutunu belirtir. Bu, bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısı olabilir.

*pParentWnd*<br/>
Animasyon denetiminin ana penceresini (genellikle a) belirtir `CDialog` . NULL olmaması gerekir.

*NID*<br/>
Animasyon denetiminin KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

`CAnimateCtrl`İki adımda oluşturursunuz. İlk olarak, oluşturucuyu çağırın ve ardından `Create` , animasyon denetimini oluşturan ve bunu nesnesine ekleyen çağırın `CAnimateCtrl` .

Animasyon denetimine aşağıdaki [pencere stillerini](../../mfc/reference/styles-used-by-mfc.md#window-styles) uygulayın.

- WS_CHILD her zaman

- Genellikle WS_VISIBLE

- WS_DISABLED nadiren

Animasyon denetiminizin genişletilmiş Windows stillerini kullanmak istiyorsanız yerine [CreateEx](#createex) çağırın `Create` .

Yukarıda listelenen pencere stillerine ek olarak, animasyon denetimine bir veya daha fazla animasyon denetim stili uygulamak isteyebilirsiniz. [Animasyon denetim stilleri](/windows/win32/Controls/animation-control-styles)hakkında daha fazla bilgi için Windows SDK bakın.

### <a name="example"></a>Örnek

  [CAnimateCtrl:: CAnimateCtrl](#canimatectrl)örneğine bakın.

## <a name="canimatectrlcreateex"></a><a name="createex"></a> CAnimateCtrl:: CreateEx

Bir denetim (alt pencere) oluşturur ve `CAnimateCtrl` nesneyle ilişkilendirir.

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
Oluşturulmakta olan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stillerinin listesi için, Windows SDK için bkz. [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) Için *dwExStyle* parametresi.

*dwStyle*<br/>
Animasyon denetiminin stilini belirtir. Windows SDK [animasyon denetim stillerinde](/windows/win32/Controls/animation-control-styles) açıklanan pencere ve animasyon denetim stillerinin herhangi bir birleşimini uygulayın.

*Rect*<br/>
*PParentWnd* istemci koordinatları içinde oluşturulacak pencerenin boyutunu ve konumunu açıklayan bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına başvuru.

*pParentWnd*<br/>
Denetimin üst öğesi olan pencerenin işaretçisi.

*NID*<br/>
Denetimin alt pencere KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CreateEx`Windows genişletilmiş stil ön yüzü **ws_ex_** tarafından belirtilen Genişletilmiş Windows stillerini uygulamak için [Create](#create) yerine kullanın.

## <a name="canimatectrlisplaying"></a><a name="isplaying"></a> CAnimateCtrl:: ısçalıyor

Audio-Video Aralanmış (AVI) klibinin çalıp oynatılmadığını gösterir.

```
BOOL IsPlaying() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir AVI klibi oynatılıyorsa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [ACM_ISPLAYING](/windows/win32/Controls/acm-isplaying) iletisini gönderir.

## <a name="canimatectrlopen"></a><a name="open"></a> CAnimateCtrl:: Open

Bir AVI klibi açmak ve ilk çerçevesini göstermek için bu işlevi çağırın.

```
BOOL Open(LPCTSTR lpszFileName);
BOOL Open(UINT nID);
```

### <a name="parameters"></a>Parametreler

*lpszFileName*<br/>
Bir `CString` nesne veya AVI dosyasının adını ya da bır avı kaynağının adını içeren null ile sonlandırılmış bir dize işaretçisi. Bu parametre NULL ise sistem, varsa animasyon denetimi için daha önce açılmış olan avı klibini kapatır.

*NID*<br/>
AVI kaynak tanımlayıcısı. Bu parametre NULL ise sistem, varsa animasyon denetimi için daha önce açılmış olan avı klibini kapatır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

AVI kaynağı, animasyon denetimini oluşturan modülden yüklenir.

`Open` bir avı klibinde sesi desteklemez; yalnızca sessiz avı kliplerini açabilirsiniz.

Animasyon denetiminin `ACS_AUTOPLAY` stili varsa, animasyon denetimi onu açtıktan hemen sonra otomatik olarak klibi yürütmeye başlayacaktır. İş yazışmanız yürütülmeye devam ederken klibi arka planda yürütmeye devam eder. Klip oynatılmaya bittiğinde otomatik olarak yinelenir.

Animasyon denetiminde `ACS_CENTER` Stil varsa, AVI klibi denetimde ortalanacak ve denetimin boyutu değişmez. Animasyon denetiminin `ACS_CENTER` stili yoksa, AVI KLIBI avı klibindeki görüntülerin boyutuna açıldığında denetim yeniden boyutlandırılır. Denetimin sol üst köşesinin konumu değişmez ve yalnızca denetimin boyutudur.

Animasyon denetiminde `ACS_TRANSPARENT` Stil varsa, ilk kare animasyon klibinde belirtilen arka plan rengi yerine saydam bir arka plan kullanılarak çizilir.

### <a name="example"></a>Örnek

  [CAnimateCtrl:: CAnimateCtrl](#canimatectrl)örneğine bakın.

## <a name="canimatectrlplay"></a><a name="play"></a> CAnimateCtrl::P Lay

Bir animasyon denetiminde bir AVI klibi oynatmak için bu işlevi çağırın.

```
BOOL Play(
    UINT nFrom,
    UINT nTo,
    UINT nRep);
```

### <a name="parameters"></a>Parametreler

*Ngüncelleştirmelerini*<br/>
Karenin oynatılmaya başladığı çerçevenin sıfır tabanlı dizini. Değer 65.536 ' den az olmalıdır. 0 değeri, AVI klibindeki ilk kareyle başlar.

*Formül*<br/>
Karenin oynatılmasının bittiği sıfır tabanlı dizini. Değer 65.536 ' den az olmalıdır. -1 değeri, AVI klibindeki son kareyle biter.

*nRep*<br/>
AVI klibini yeniden yürütme sayısı. -1 değeri, dosyayı süresiz olarak yeniden oynamanın anlamına gelir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

İş yazışmanız yürütülmeye devam ederken animasyon denetimi klibi arka planda oynatacak. Animasyon denetiminin `ACS_TRANSPARENT` stili varsa, AVI klibi animasyon klibinde belirtilen arka plan rengi yerine saydam bir arka plan kullanılarak yürütülür.

### <a name="example"></a>Örnek

  [CAnimateCtrl:: CAnimateCtrl](#canimatectrl)örneğine bakın.

## <a name="canimatectrlseek"></a><a name="seek"></a> CAnimateCtrl:: Seek

AVI klibinizin tek bir çerçevesini statik olarak göstermek için bu işlevi çağırın.

```
BOOL Seek(UINT nTo);
```

### <a name="parameters"></a>Parametreler

*Formül*<br/>
Görüntülenecek çerçevenin sıfır tabanlı dizini. Değer 65.536 ' den az olmalıdır. 0 değeri, AVI klibindeki ilk kareyi gösterir anlamına gelir. -1 değeri, AVI klibinde son kareyi gösterir anlamına gelir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Animasyon denetiminde `ACS_TRANSPARENT` Stil varsa, AVI klibi animasyon klibinde belirtilen arka plan rengi yerine saydam bir arka plan kullanılarak çizilir.

### <a name="example"></a>Örnek

[CAnimateCtrl:: CAnimateCtrl](#canimatectrl)örneğine bakın.

## <a name="canimatectrlstop"></a><a name="stop"></a> CAnimateCtrl:: stop

Bir animasyon denetiminde bir avı klibini çalmayı durdurmak için bu işlevi çağırın.

```
BOOL Stop();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="example"></a>Örnek

  [CAnimateCtrl:: CAnimateCtrl](#canimatectrl)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CWnd sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CAnimateCtrl:: Create](#create)<br/>
[ON_CONTROL](message-map-macros-mfc.md#on_control)
