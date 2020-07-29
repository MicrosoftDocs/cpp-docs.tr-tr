---
title: CBitmapButton sınıfı
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
ms.openlocfilehash: 0cf4554f86f4a9275e4d96b3db519fde7fb05b22
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231877"
---
# <a name="cbitmapbutton-class"></a>CBitmapButton sınıfı

Metin yerine biteşlenmiş görüntülerle etiketlenmiş basma düğmeli denetimleri oluşturur.

## <a name="syntax"></a>Sözdizimi

```
class CBitmapButton : public CButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CBitmapButton:: CBitmapButton](#cbitmapbutton)|Bir `CBitmapButton` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CBitmapButton:: oto Load](#autoload)|İletişim kutusu içindeki bir düğmeyi, sınıfının bir nesnesiyle ilişkilendirir `CBitmapButton` , bitmapi ada göre yükler ve düğmeyi bit eşlemle sığacak şekilde boyutlandırır.|
|[CBitmapButton:: Loadbitmapler](#loadbitmaps)|Uygulamanın kaynak dosyasından bir veya daha fazla adlandırılmış bit eşlem kaynağı yükleyerek ve bit eşlemleri nesnesine ekleyerek nesneyi başlatır.|
|[CBitmapButton:: SizeToContent](#sizetocontent)|Düğmeyi bit eşlemle sığacak şekilde boyutlandırır.|

## <a name="remarks"></a>Açıklamalar

`CBitmapButton`nesneler, farklı durumların görüntülerini içeren en fazla dört bit eşlem içerir. bir düğme, (veya normal), aşağı (veya seçili), odaklanmış ve devre dışı olarak kabul edilebilir. Yalnızca ilk bit eşlem gereklidir; Diğerleri isteğe bağlıdır.

Bit eşlem düğmesi görüntüleri görüntünün etrafındaki ve görüntünün etrafında kenarlık içerir. Kenarlık genellikle düğmenin durumunu gösteren bir bölüm oynar. Örneğin, odaklanmış durum için bit eşlem genellikle, yukarı durumu için, ancak kenardan kesik çizgili bir dikdörtgen ya da kenarlıkta kalın bir düz çizgi ile aynıdır. Devre dışı bırakılan durum için bit eşlem genellikle en düşük bir kontrast (soluk veya gri bir menü seçimi gibi) içerir.

Bu bit eşlemler herhangi bir boyutta olabilir, ancak tümü, yukarı durum için bit eşlemle aynı boyutta gibi davranır.

Çeşitli uygulamalar, farklı bit eşlem görüntülerinin birleşimlerini talep altına alarak:

|Yukarı|Aşağı|Odaklı|Devre dışı|Uygulama|
|--------|----------|-------------|--------------|-----------------|
|×||||Biteş|
|×|×|||WS_TABSTOP stili olmayan düğme|
|×|×|×|×|Tüm durumlarıyla iletişim kutusu düğmesi|
|×|×|×||WS_TABSTOP stiliyle iletişim kutusu düğmesi|

Bit eşlem düğme denetimi oluştururken, düğmenin sahip olarak çizildiğini belirtmek için BS_OWNERDRAW stilini ayarlayın. Bu, Windows 'un düğme için WM_MEASUREITEM ve WM_DRAWITEM iletilerini göndermesini sağlar; Framework bu iletileri işler ve düğmenin görünümünü yönetir.

### <a name="to-create-a-bitmap-button-control-in-a-windows-client-area"></a>Bir pencerenin istemci alanında bir bit eşlem düğmesi denetimi oluşturmak için

1. Düğme için bir-dört bit eşlem görüntüsü oluşturun.

1. [CBitmapButton](#cbitmapbutton) nesnesini oluşturun.

1. Windows düğme denetimini oluşturmak ve nesneye iliştirmek için [Oluştur](../../mfc/reference/cbutton-class.md#create) işlevini çağırın `CBitmapButton` .

1. Bit eşlem düğmesi oluşturulduktan sonra bit eşlem kaynaklarını yüklemek için [Loadbitmap'ler](#loadbitmaps) üye işlevini çağırın.

### <a name="to-include-a-bitmap-button-control-in-a-dialog-box"></a>Bir iletişim kutusuna bir bit eşlem düğmesi denetimi eklemek için

1. Düğme için bir-dört bit eşlem görüntüsü oluşturun.

1. Bir sahip çiz düğmesine sahip bir iletişim şablonu oluşturun ve bu düğme, bit eşlem düğmesine istediğiniz yere yerleştirilir. Şablondaki düğmenin boyutu önemi yoktur.

1. Düğmenin başlığını "MYıMAGE" gibi bir değere ayarlayın ve düğme için IDC_MYIMAGE gibi bir simge tanımlayın.

1. Uygulamanızın kaynak komut dosyasında, adım 3 ' teki düğme başlığı için kullanılan dizeye "U," "D," "F" veya "X" (yukarı, aşağı, odaklanmış ve devre dışı) harflerinden birini ekleyerek oluşturulan düğme için oluşturulan her bir görüntünün KIMLIĞINI verin. "MYıMAGE" düğme başlığı için, kimlikler "MYıMAGEU," "MYıMAŞLı," "MYıMAGEF" ve "MYıMAGEX" şeklinde olur. Bit eşlemlerinizin KIMLIĞINI çift tırnak içinde belirtmeniz **gerekir** . Aksi takdirde, kaynak Düzenleyicisi kaynağa bir tamsayı atar ve görüntü yüklenirken MFC başarısız olur.

1. Uygulamanızın iletişim kutusu sınıfında (öğesinden türetilir `CDialog` ), `CBitmapButton` üye nesnesi ekleyin.

1. `CDialog`Nesnenin [OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog) yordamında, `CBitmapButton` düğmenin denetim kimliği ve nesne işaretçisinin parametre olarak kullanıldığı nesnenin [oto Load](#autoload) işlevini çağırın `CDialog` **`this`** .

Bit eşlem düğmesi denetimi tarafından üst öğesine (genellikle öğesinden türetilmiş bir sınıf) gönderilen BN_CLICKED gibi Windows bildirim iletilerini işlemek istiyorsanız `CDialog` , `CDialog` her ileti için bir ileti eşleme girişi ve ileti işleyici üye işlevi ile türetilmiş nesneye ekleyin. Bir nesne tarafından gönderilen bildirimler `CBitmapButton` bir [CButton](../../mfc/reference/cbutton-class.md) nesnesi tarafından gönderilen olanlarla aynıdır.

[CToolBar](../../mfc/reference/ctoolbar-class.md) sınıfı, bit eşlem düğmelerine farklı bir yaklaşım alır.

Hakkında daha fazla bilgi için `CBitmapButton` bkz. [denetimler](../../mfc/controls-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

`CBitmapButton`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext. h

## <a name="cbitmapbuttonautoload"></a><a name="autoload"></a>CBitmapButton:: oto Load

İletişim kutusu içindeki bir düğmeyi, sınıfının bir nesnesiyle ilişkilendirir `CBitmapButton` , bitmapi ada göre yükler ve düğmeyi bit eşlemle sığacak şekilde boyutlandırır.

```
BOOL AutoLoad(
    UINT nID,
    CWnd* pParent);
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
Düğmenin denetim KIMLIĞI.

*pParent*<br/>
Düğmenin sahibi olan nesneye yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`AutoLoad`İletişim kutusunda bir sahip Çiz düğmesini bir bit eşlem düğmesi olarak başlatmak için işlevini kullanın. Bu işlevi kullanmaya yönelik yönergeler, sınıfının açıklamalardır `CBitmapButton` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#75](../../mfc/codesnippet/cpp/cbitmapbutton-class_1.cpp)]

## <a name="cbitmapbuttoncbitmapbutton"></a><a name="cbitmapbutton"></a>CBitmapButton:: CBitmapButton

Bir `CBitmapButton` nesnesi oluşturur.

```
CBitmapButton();
```

### <a name="remarks"></a>Açıklamalar

C++ nesnesini oluşturduktan sonra `CBitmapButton` , Windows düğme denetimini oluşturmak ve nesneye iliştirmek Için [CButton:: Create](../../mfc/reference/cbutton-class.md#create) öğesini çağırın `CBitmapButton` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#57](../../mfc/codesnippet/cpp/cbitmapbutton-class_2.cpp)]

## <a name="cbitmapbuttonloadbitmaps"></a><a name="loadbitmaps"></a>CBitmapButton:: Loadbitmapler

Kaynak adlarına veya KIMLIK numaralarına göre tanımlanan bit eşlem görüntülerini yüklemek istediğinizde veya işlevini kullanamıyorsa, `AutoLoad` Örneğin bir iletişim kutusunun parçası olmayan bir bit eşlem düğmesi oluşturduğunuz zaman bu işlevi kullanın.

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
Bit eşlem düğmesinin normal veya "Up" durumu için bit eşlemin adını içeren null ile sonlandırılmış dizeyi işaret eder. Gereklidir.

*lpszBitmapResourceSel*<br/>
Bit eşlem düğmesinin seçili veya "aşağı" durumunun bit eşlem adını içeren null ile sonlandırılmış dizeyi işaret eder. NULL olabilir.

*lpszBitmapResourceFocus*<br/>
Bit eşlem düğmesinin odaklanmış durumunun bit eşlem adını içeren null ile sonlandırılmış dizeyi işaret eder. NULL olabilir.

*lpszBitmapResourceDisabled*<br/>
Bit eşlem düğmesinin devre dışı durumunun bit eşlem adını içeren null ile sonlandırılmış dizeyi işaret eder. NULL olabilir.

*Nıdbitmapresource*<br/>
Bit eşlem düğmesinin normal veya "Up" durumu için bit eşlem kaynağının kaynak KIMLIĞI numarasını belirtir. Gereklidir.

*Nıdbitmapresourcesel*<br/>
Bit eşlem düğmesinin seçili veya "aşağı" durumundaki bit eşlem kaynağının kaynak KIMLIĞI numarasını belirtir. 0 olabilir.

*Nıdbitmapresourcefocus*<br/>
Bit eşlem düğmesinin odaklanmış durumu için bit eşlem kaynağının kaynak KIMLIĞI numarasını belirtir. 0 olabilir.

*Nıdbitmapresourcedisabled*<br/>
Bit eşlem düğmesinin devre dışı durumu için bit eşlem kaynağının kaynak KIMLIĞI numarasını belirtir. 0 olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#58](../../mfc/codesnippet/cpp/cbitmapbutton-class_3.cpp)]

## <a name="cbitmapbuttonsizetocontent"></a><a name="sizetocontent"></a>CBitmapButton:: SizeToContent

Bit eşlem düğmesini bit eşlem boyutuna göre yeniden boyutlandırmak için bu işlevi çağırın.

```cpp
void SizeToContent();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#59](../../mfc/codesnippet/cpp/cbitmapbutton-class_4.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CTRLTEST](../../overview/visual-cpp-samples.md)<br/>
[CButton sınıfı](../../mfc/reference/cbutton-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
