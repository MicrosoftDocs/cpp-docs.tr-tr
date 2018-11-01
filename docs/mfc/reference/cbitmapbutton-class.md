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
ms.openlocfilehash: 6bff87cd7648e1e5f4e0391a0a7fc1a1455a51f0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599660"
---
# <a name="cbitmapbutton-class"></a>CBitmapButton sınıfı

Metin yerine bit eşlemli görüntülerle etiketlenmiş pushbutton denetimleri oluşturur.

## <a name="syntax"></a>Sözdizimi

```
class CBitmapButton : public CButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CBitmapButton::CBitmapButton](#cbitmapbutton)|Oluşturur bir `CBitmapButton` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CBitmapButton::AutoLoad](#autoload)|Bir düğme bir iletişim kutusunda bir nesne ile ilişkilendirir `CBitmapButton` sınıf adına göre bitmap(s) yükler ve bit eşlem sığdırmak için düğmeyi boyutları.|
|[CBitmapButton::LoadBitmaps](#loadbitmaps)|Uygulamanın kaynak dosyasından bir veya daha fazla adlandırılmış bit eşlemi Kaynak yükleniyor ve nesneye bit eşlemler ekleme nesnesini başlatır.|
|[CBitmapButton::SizeToContent](#sizetocontent)|Bit eşlem için uyum sağlamak için düğmeyi boyutlandırır.|

## <a name="remarks"></a>Açıklamalar

`CBitmapButton` nesneleri içeren bir düğme varsayabilirsiniz farklı durumlar için görüntüleri içeren en fazla dört bit eşlemler: Yukarı (veya normal) aşağı (veya seçili) odaklanır ve devre dışı. Yalnızca ilk bit eşlem gereklidir; diğerleri isteğe bağlıdır.

Bit eşlem düğmesi görüntüleri görüntünün yanı sıra Görüntünün kendisi çevresinde kenarlık içerir. Kenarlık genellikle düğme durumunu gösteren bir yer yürütür. Örneğin, bit eşlem odaklanmış durumu için genellikle bir yukarı durumu için ancak border veya kalın Kesiksiz bir çizgi kenarlık, bir kesikli dikdörtgen iç gibidir. Devre dışı genellikle durum için bit eşlem yukarı durumu ancak daha düşük Karşıtlık (gibi soluk gri menüsü seçim) için bir benzer.

Bu bit eşlemler herhangi bir boyutta olabilir, ancak aynı boyutta yukarı durumu için bit eşlem değilmiş gibi davranılır.

Çeşitli uygulamalar, bit eşlem resimleri farklı birleşimlerini talep:

|Ayarlama|Aşağı|Odaklanmış|Devre dışı|Uygulama|
|--------|----------|-------------|--------------|-----------------|
|×||||Bit eşlem|
|×|×|||WS_TABSTOP stil olmadan düğmesi|
|×|×|×|×|Tüm durumlar iletişim düğmesi|
|×|×|×||WS_TABSTOP stiliyle iletişim düğmesi|

Bir bit eşlem düğmesi denetimi oluştururken, düğmenin özelleştirilmiş olarak çizilen olduğunu belirtmek için BS_OWNERDRAW stilini ayarlayın. Bu düğme için WM_MEASUREITEM ve WM_DRAWITEM ileti göndermek Windows neden olur; framework, bu iletileri işleyen ve sizin için düğmenin görünümünü yönetir.

### <a name="to-create-a-bitmap-button-control-in-a-windows-client-area"></a>Bir pencerenin istemci alanında bir bit eşlem düğmesi denetimi oluşturmak için

1. Bir ile dört düğme için bit eşlem resimleri oluşturun.

1. Oluşturmak [CBitmapButton](#cbitmapbutton) nesne.

1. Çağrı [Oluştur](../../mfc/reference/cbutton-class.md#create) Windows düğme denetimini oluşturup buna eklemek için işlevi `CBitmapButton` nesne.

1. Çağrı [LoadBitmaps](#loadbitmaps) bit eşlemi Kaynak bit eşlem düğmesi oluşturulmuş sonra yüklemek için üye işlevi.

### <a name="to-include-a-bitmap-button-control-in-a-dialog-box"></a>İletişim kutusunda bir bit eşlem düğme denetimi eklemek için

1. Bir ile dört düğme için bit eşlem resimleri oluşturun.

1. Bit eşlem düğmesi istediğiniz konumlandırılmış bir özelleştirilmiş çizimli düğmesi ile bir iletişim şablonunu oluşturun. Şablondaki düğmenin boyutu önemli değildir.

1. Düğmenin resim yazısı "MYIMAGE" gibi bir değere ayarlayın ve IDC_MYIMAGE gibi düğme için bir simge tanımlayabilirsiniz.

1. Uygulamanızın kaynak betiği her düğme için oluşturulmuş bir harf "U", "D", "F" ekleyerek bir kimliği oluşturulan görüntüleri vermek ya da "X" (yukarı, aşağı, odaklanır ve devre dışı için) düğmesi başlığı için kullanılan dize için 3. adım. Düğmesi başlığı "MYIMAGE", örneğin, kimlikleri "MYIMAGEU", "MYIMAGED," olacaktır "MYIMAGEF" ve "MYIMAGEX." **Gerekir** çift tırnak içinde bit eşlemler Kimliğini belirtin. Aksi takdirde kaynak düzenleyicisini tamsayı kaynağa atar ve MFC görüntü yüklenirken başarısız olur.

1. Uygulamanızın iletişim sınıfında (türetilen `CDialog`), ekleme bir `CBitmapButton` üye nesnesi.

1. İçinde `CDialog` nesnenin [OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog) rutin, çağrı `CBitmapButton` nesnenin [Sorsorgu](#autoload) işlev, parametre olarak düğmenin denetim Kimliğini kullanarak ve `CDialog` nesnenin **bu** işaretçi.

BN_CLICKED, örneğin Windows bildirim iletilerini işlemek isterseniz bir bit eşlem düğmesi denetimi tarafından üstüne gönderilir (öğesinden türetilmiş bir sınıf genellikle `CDialog`), ekleme `CDialog`-türetilmiş nesneden bir ileti eşleme girişi ve ileti işleyicisi üyesi her ileti için işlev. Tarafından gönderilen bildirimleri bir `CBitmapButton` nesne tarafından gönderilen bu aynı olan bir [CButton](../../mfc/reference/cbutton-class.md) nesne.

Sınıf [CToolBar](../../mfc/reference/ctoolbar-class.md) farklı bir yaklaşım için bit eşlem düğmeler alır.

Daha fazla bilgi için `CBitmapButton`, bkz: [denetimleri](../../mfc/controls-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

`CBitmapButton`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxext.h

##  <a name="autoload"></a>  CBitmapButton::AutoLoad

Bir düğme bir iletişim kutusunda bir nesne ile ilişkilendirir `CBitmapButton` sınıf adına göre bitmap(s) yükler ve bit eşlem sığdırmak için düğmeyi boyutları.

```
BOOL AutoLoad(
    UINT nID,
    CWnd* pParent);
```

### <a name="parameters"></a>Parametreler

*nID*<br/>
Düğmenin denetim kimliği.

*pParent*<br/>
Düğmeye sahip bir nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Kullanım `AutoLoad` iletişim kutusunda bir bit eşlem düğmesi olarak bir özelleştirilmiş çizimli düğmesi işlevi. Açıklamalar için bu işlevi kullanmak için yönergeler bulunduğunuz `CBitmapButton` sınıfı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#75](../../mfc/codesnippet/cpp/cbitmapbutton-class_1.cpp)]

##  <a name="cbitmapbutton"></a>  CBitmapButton::CBitmapButton

Oluşturur bir `CBitmapButton` nesne.

```
CBitmapButton();
```

### <a name="remarks"></a>Açıklamalar

C++ oluşturduktan sonra `CBitmapButton` nesne, çağrı [CButton::Create](../../mfc/reference/cbutton-class.md#create) Windows düğme denetimini oluşturup buna eklemek için `CBitmapButton` nesne.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#57](../../mfc/codesnippet/cpp/cbitmapbutton-class_2.cpp)]

##  <a name="loadbitmaps"></a>  CBitmapButton::LoadBitmaps

Kaynak adları veya kimlik numaraları veya kullanamazsınız, tanımlanan bit eşlem resimleri yüklemek istediğinizde, bu işlevi kullanın `AutoLoad` Örneğin, bir iletişim kutusu bir parçası olmayan bir bit eşlem düğmesi oluşturmak için işlev.

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
Bit eşlemin bir bit eşlem düğmenin normal veya "çalışır" durumda adında boş sonlandırılmış dizeye işaret eder. Gerekli.

*lpszBitmapResourceSel*<br/>
"Kapalı" durumu ya da bir bit eşlem düğmesi seçilen için bit eşlem adını içeren null ile sonlandırılmış dizeye işaret eder. NULL olabilir.

*lpszBitmapResourceFocus*<br/>
Bit eşlem bit eşlem düğmenin adını içeren null ile sonlandırılmış dize noktalarına durumu odaklanır. NULL olabilir.

*lpszBitmapResourceDisabled*<br/>
Bit eşlem bit eşlem düğmenin devre dışı bırakılmış adını içeren boş sonlandırılmış dizeye işaret eder. NULL olabilir.

*nIDBitmapResource*<br/>
Bir bit eşlem düğmenin normal veya "çalışır" durumda bit eşlem kaynağının kaynak kimliği numarasını belirtir. Gerekli.

*nIDBitmapResourceSel*<br/>
Bir bit eşlem düğmesi seçili veya "kapalı" durumu bit eşlem kaynağının kaynak kimliği numarasını belirtir. 0 olabilir.

*nIDBitmapResourceFocus*<br/>
Odaklanmış bir bit eşlem düğmenin durumu için bit eşlem kaynağının kaynak kimliği numarasını belirtir. 0 olabilir.

*nIDBitmapResourceDisabled*<br/>
Bir bit eşlem düğmenin devre dışı durumu için bit eşlem kaynağının kaynak kimliği numarasını belirtir. 0 olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#58](../../mfc/codesnippet/cpp/cbitmapbutton-class_3.cpp)]

##  <a name="sizetocontent"></a>  CBitmapButton::SizeToContent

Bir bit eşlem düğmesi bit eşlemin bir boyuta yeniden boyutlandırmak için bu işlevi çağırın.

```
void SizeToContent();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#59](../../mfc/codesnippet/cpp/cbitmapbutton-class_4.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek CTRLTEST](../../visual-cpp-samples.md)<br/>
[CButton Sınıfı](../../mfc/reference/cbutton-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

