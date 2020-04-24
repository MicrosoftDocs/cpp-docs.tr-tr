---
title: CBitmapButton Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CBitmapButton
- AFXEXT/CBitmapButton
- AFXEXT/CBitmapButton::CBitmapButton
- AFXEXT/CBitmapButton::AutoLoad
- AFXEXT/CBitmapButton::LoadBitmaps
- AFXEXT/CBitmapButton::SizeToContent
helpviewer_keywords:
- CBitmapButton [MFC], CBitmapButton
- CBitmapButton [MFC], AutoLoad
- CBitmapButton [MFC], LoadBitmaps
- CBitmapButton [MFC], SizeToContent
ms.assetid: 9ad6cb45-c3c4-4fb1-96d3-1fe3df7bbcfc
ms.openlocfilehash: df21591dec1da5861125d7e9480fb9345aaad061
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752955"
---
# <a name="cbitmapbutton-class"></a>CBitmapButton Sınıfı

Metin yerine biteşe görüntülerle etiketlenmiş düğme denetimleri oluşturur.

## <a name="syntax"></a>Sözdizimi

```
class CBitmapButton : public CButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CBitmapButton::CBitmapButton](#cbitmapbutton)|Bir `CBitmapButton` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CBitmapButton::Otomatik Yükleme](#autoload)|İletişim kutusundaki bir düğmeyi `CBitmapButton` sınıfın bir nesnesiyle ilişkilendirin, bitmap(ler)'i ada göre yükler ve düğmeyi bit eşlebe sığdırmak için boyutlandırır.|
|[CBitmapButton::LoadBitmaps](#loadbitmaps)|Uygulamanın kaynak dosyasından bir veya daha fazla adlandırılmış bit eşlem kaynaklarını yükleyerek ve bit eşlemlerini nesneye ekleyerek nesneyi başlatır.|
|[CBitmapButton::SizeToContent](#sizetocontent)|Bit eşlemi sığdırmak için düğmeyi boyutlar.|

## <a name="remarks"></a>Açıklamalar

`CBitmapButton`nesneler, bir düğmenin varsayabileceği farklı durumlar için görüntüler içeren en fazla dört bit eşlem içerir: yukarı (veya normal), aşağı (veya seçili), odaklanmış ve devre dışı bırakılmış. Yalnızca ilk bit eşlemi gereklidir; diğerleri isteğe bağlıdır.

Bitmap düğmesi görüntüleri, görüntünün etrafındaki kenarlığı ve görüntünün kendisini içerir. Kenarlık genellikle düğmenin durumunu göstermede rol oynar. Örneğin, odaklanmış durum için bitmap genellikle yukarı durum için bir gibi, ancak kenarlığı veya sınırda kalın bir düz çizgi bir kesikli dikdörtgen inset ile. Devre dışı bırakılmış durum için bit eşlemi genellikle yukarı durumu için olana benzer, ancak daha düşük kontrasta sahiptir (soluk veya gri menü seçimi gibi).

Bu bit eşlemler herhangi bir boyutta olabilir, ancak hepsi yukarı durum için bit eşlemle aynı boyuttaymuş gibi değerlendirilir.

Çeşitli uygulamalar bitmap görüntülerinin farklı kombinasyonlarını ister:

|Yukarı|Aşağı|Odaklı|Devre dışı|Uygulama|
|--------|----------|-------------|--------------|-----------------|
|×||||Bitmap|
|×|×|||WS_TABSTOP tarzı olmadan düğme|
|×|×|×|×|Tüm durumları içeren iletişim düğmesi|
|×|×|×||WS_TABSTOP stili olan iletişim düğmesi|

Bitmap düğmesi denetimi oluştururken, düğmenin sahiptarafından çizildiğini belirtmek için BS_OWNERDRAW stilini ayarlayın. Bu, Windows'un düğme için WM_MEASUREITEM ve WM_DRAWITEM iletiler göndermesine neden olur; çerçeve bu iletileri işler ve sizin için düğmenin görünümünü yönetir.

### <a name="to-create-a-bitmap-button-control-in-a-windows-client-area"></a>Pencerenin istemci alanında bitmap düğmesi denetimi oluşturmak için

1. Düğme için bir ila dört biteşlik görüntü oluşturun.

1. [CBitmapButton](#cbitmapbutton) nesnesini oluştur.

1. Windows [Create](../../mfc/reference/cbutton-class.md#create) düğmesi denetimini oluşturmak ve `CBitmapButton` nesneye takmak için Oluştur işlevini arayın.

1. Bitmap düğmesi oluşturulduktan sonra bitmap kaynaklarını yüklemek için [LoadBitmaps](#loadbitmaps) üye işlevini arayın.

### <a name="to-include-a-bitmap-button-control-in-a-dialog-box"></a>İletişim kutusuna bitmap düğmesi denetimi eklemek için

1. Düğme için bir ila dört biteşlik görüntü oluşturun.

1. Bitmap düğmesini istediğiniz yerde konumlandırılmış bir sahip çizim düğmesi içeren bir iletişim şablonu oluşturun. Şablondaki düğmenin boyutu önemli değildir.

1. Düğmenin başlığını "MYIMAGE" gibi bir değere ayarlayın ve IDC_MYIMAGE gibi düğme için bir sembol tanımlayın.

1. Uygulamanızın kaynak komut dosyasında, "U", "D", "F" veya "X" (yukarı, aşağı, odaklanmış ve devre dışı bırakılmış için) harflerinden birini adım 3'teki düğme başlığı için kullanılan dize ekleyerek oluşturulan düğme için oluşturulan görüntülerin her birini bir kimlik verin. "MYIMAGE" butonu için, örneğin, "MYIMAGEU", " MYIMAGED", " MYIMAGEF" ve " MYIMAGEX" olacaktır. Bitmaps'inizin kimliğini çift tırnak içinde **belirtmeniz gerekir.** Aksi takdirde kaynak düzenleyicisi kaynağa bir arametatar ve görüntüyü yüklerken MFC başarısız olur.

1. Uygulamanızın iletişim sınıfında (türetilmiş), `CDialog`bir `CBitmapButton` üye nesne ekleyin.

1. Nesnenin `CDialog` [OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog) yordamında, `CBitmapButton` parametre olarak düğmenin denetim kimliğini ve nesnenin `CDialog` **bu** işaretçisini kullanarak nesnenin [AutoLoad](#autoload) işlevini arayın.

BN_CLICKED gibi, bitmap düğmesi denetimi tarafından üst öğesine (genellikle türetilen bir sınıf) gönderilen `CDialog`Windows bildirim `CDialog`iletilerini işlemek istiyorsanız, türetilmiş nesneye her ileti için bir ileti eşlemi girişi ve ileti işleyicisi üye işlevi ekleyin. Bir `CBitmapButton` nesne tarafından gönderilen bildirimler, [CButton](../../mfc/reference/cbutton-class.md) nesnesi tarafından gönderilenlerle aynıdır.

[CToolBar](../../mfc/reference/ctoolbar-class.md) sınıfı bitmap düğmelerine farklı bir yaklaşım benimser.

Daha fazla `CBitmapButton`bilgi için Bkz. [Denetimler.](../../mfc/controls-mfc.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cbutton](../../mfc/reference/cbutton-class.md)

`CBitmapButton`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext.h

## <a name="cbitmapbuttonautoload"></a><a name="autoload"></a>CBitmapButton::Otomatik Yükleme

İletişim kutusundaki bir düğmeyi `CBitmapButton` sınıfın bir nesnesiyle ilişkilendirin, bitmap(ler)'i ada göre yükler ve düğmeyi bit eşlebe sığdırmak için boyutlandırır.

```
BOOL AutoLoad(
    UINT nID,
    CWnd* pParent);
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
Düğmenin kontrol kimliği.

*pParent*<br/>
Düğmenin sahibi nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İletişim `AutoLoad` kutusundaki sahip çizim düğmesini bitmap düğmesi olarak başlatmak için işlevi kullanın. Bu işlevi kullanma yönergeleri sınıfın açıklamalarında yer alıyor. `CBitmapButton`

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#75](../../mfc/codesnippet/cpp/cbitmapbutton-class_1.cpp)]

## <a name="cbitmapbuttoncbitmapbutton"></a><a name="cbitmapbutton"></a>CBitmapButton::CBitmapButton

Bir `CBitmapButton` nesnesi oluşturur.

```
CBitmapButton();
```

### <a name="remarks"></a>Açıklamalar

C++ `CBitmapButton` nesnesini oluşturduktan sonra [CButton'u arayın::Windows](../../mfc/reference/cbutton-class.md#create) düğmesi denetimini oluşturmak ve `CBitmapButton` nesneye takmak için oluştur' un.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#57](../../mfc/codesnippet/cpp/cbitmapbutton-class_2.cpp)]

## <a name="cbitmapbuttonloadbitmaps"></a><a name="loadbitmaps"></a>CBitmapButton::LoadBitmaps

Kaynak adlarıyla veya kimlik numaralarıyla tanımlanan bitmap görüntülerini yüklemek istediğinizde veya `AutoLoad` örneğin iletişim kutusunun parçası olmayan bir bitmap düğmesi oluşturduğunuz için işlevi kullanamadığınızda bu işlevi kullanın.

```
BOOL LoadBitmaps(
    LPCTSTR lpszBitmapResource,
    LPCTSTR lpszBitmapResourceSel = NULL,
    LPCTSTR lpszBitmapResourceFocus = NULL,
    LPCTSTR lpszBitmapResourceDisabled = NULL);

BOOL LoadBitmaps(
    UINT nIDBitmapResource,
    UINT nIDBitmapResourceSel = 0,
    UINT nIDBitmapResourceFocus = 0,
    UINT nIDBitmapResourceDisabled = 0);
```

### <a name="parameters"></a>Parametreler

*lpszBitmapResource*<br/>
Bitmap düğmesinin normal veya "yukarı" durumu için bit eşlem adını içeren null-sonlandırılan dizeyi işaret eder. Gereklidir.

*lpszBitmapResourceSel*<br/>
Bitmap düğmesinin seçili veya "aşağı" durumu için bit eşlem adını içeren null-sonlandırılan dizeyi işaret eder. NULL olabilir.

*lpszBitmapResourceFocus*<br/>
Bitmap düğmesinin odaklanmış durumu için bit eşlem adını içeren null-sonlandırılan dizeyi işaret eder. NULL olabilir.

*lpszBitmapResourceDevre Dışı*<br/>
Bitmap düğmesinin devre dışı bırakılmış durumu için bit eşlem adını içeren null-sonlandırılan dizeyi işaret eder. NULL olabilir.

*nIDBitmapResource*<br/>
Bitmap düğmesinin normal veya "yukarı" durumu için biteşkaynağıkaynağının kaynak kimlik numarasını belirtir. Gereklidir.

*nIDBitmapResourceSel*<br/>
Bitmap düğmesinin seçili veya "aşağı" durumu için biteşkaynağıkaynağının kaynak kimlik numarasını belirtir. 0 olabilir.

*nIDBitmapResourceFocus*<br/>
Bitmap düğmesinin odaklanmış durumu için biteşkaynağının kaynak kimlik numarasını belirtir. 0 olabilir.

*nIDBitmapResourceDevre Dışı*<br/>
Bitmap düğmesinin devre dışı bırakılmış durumu için biteşkaynağıkaynağının kaynak kimlik numarasını belirtir. 0 olabilir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#58](../../mfc/codesnippet/cpp/cbitmapbutton-class_3.cpp)]

## <a name="cbitmapbuttonsizetocontent"></a><a name="sizetocontent"></a>CBitmapButton::SizeToContent

Bitmap düğmesini bit eşlemi boyutuna yeniden boyutlandırmak için bu işlevi arayın.

```cpp
void SizeToContent();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#59](../../mfc/codesnippet/cpp/cbitmapbutton-class_4.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek CTRLTEST](../../overview/visual-cpp-samples.md)<br/>
[CButton Sınıfı](../../mfc/reference/cbutton-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
