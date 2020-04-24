---
title: CPictureHolder Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CPictureHolder
- AFXCTL/CPictureHolder
- AFXCTL/CPictureHolder::CPictureHolder
- AFXCTL/CPictureHolder::CreateEmpty
- AFXCTL/CPictureHolder::CreateFromBitmap
- AFXCTL/CPictureHolder::CreateFromIcon
- AFXCTL/CPictureHolder::CreateFromMetafile
- AFXCTL/CPictureHolder::GetDisplayString
- AFXCTL/CPictureHolder::GetPictureDispatch
- AFXCTL/CPictureHolder::GetType
- AFXCTL/CPictureHolder::Render
- AFXCTL/CPictureHolder::SetPictureDispatch
- AFXCTL/CPictureHolder::m_pPict
helpviewer_keywords:
- CPictureHolder [MFC], CPictureHolder
- CPictureHolder [MFC], CreateEmpty
- CPictureHolder [MFC], CreateFromBitmap
- CPictureHolder [MFC], CreateFromIcon
- CPictureHolder [MFC], CreateFromMetafile
- CPictureHolder [MFC], GetDisplayString
- CPictureHolder [MFC], GetPictureDispatch
- CPictureHolder [MFC], GetType
- CPictureHolder [MFC], Render
- CPictureHolder [MFC], SetPictureDispatch
- CPictureHolder [MFC], m_pPict
ms.assetid: a4f59775-704a-41dd-b5bd-2e531c95127a
ms.openlocfilehash: edb93b05c1187d2c78f4c1120ee76282167c9b49
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753603"
---
# <a name="cpictureholder-class"></a>CPictureHolder Sınıfı

Kullanıcının denetiminizde bir resim görüntülemesine olanak tanıyan bir Resim özelliği uygular.

## <a name="syntax"></a>Sözdizimi

```
class CPictureHolder
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CPictureHolder::CPictureHolder](#cpictureholder)|Bir `CPictureHolder` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CPictureHolder::CreateEmpty](#createempty)|Boş `CPictureHolder` bir nesne oluşturur.|
|[CPictureHolder::CreateFromBitmap](#createfrombitmap)|Bir bit `CPictureHolder` haritasından bir nesne oluşturur.|
|[CPictureHolder::CreateFromIcon](#createfromicon)|Simgeden `CPictureHolder` bir nesne oluşturur.|
|[CPictureHolder::CreateFromMetafile](#createfrommetafile)|Meta dosyadan bir `CPictureHolder` nesne oluşturur.|
|[CPictureHolder::GetDisplayString](#getdisplaystring)|Denetim kapsayıcısının özellik tarayıcısında görüntülenen dizeyi alır.|
|[CPictureHolder::GetPictureDispatch](#getpicturedispatch)|Nesnenin `CPictureHolder` `IDispatch` arabirimini döndürür.|
|[CPictureHolder::GetType](#gettype)|Nesnenin `CPictureHolder` bir biteşmi, meta dosya mı yoksa simge mi olduğunu söyler.|
|[CPictureHolder::Render](#render)|Resmi işler.|
|[CPictureHolder::SetPictureDispatch](#setpicturedispatch)|Nesnenin `CPictureHolder` `IDispatch` arabirimini ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CPictureHolder::m_pPict](#m_ppict)|Resim nesnesine işaretçi.|

## <a name="remarks"></a>Açıklamalar

`CPictureHolder`taban sınıfa sahip değildir.

Stok Resim özelliği yle, geliştirici görüntülenmek üzere bir bit eşlemi, simge veya metadosya belirtebilir.

Özel resim özellikleri oluşturma hakkında daha fazla bilgi için [MFC ActiveX Denetimleri makalesine bakın: ActiveX Denetiminde Resimleri Kullanma.](../../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CPictureHolder`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxctl.h

## <a name="cpictureholdercpictureholder"></a><a name="cpictureholder"></a>CPictureHolder::CPictureHolder

Bir `CPictureHolder` nesne inşa eder.

```
CPictureHolder();
```

## <a name="cpictureholdercreateempty"></a><a name="createempty"></a>CPictureHolder::CreateEmpty

Boş `CPictureHolder` bir nesne oluşturur ve bir `IPicture` arabirime bağlanır.

```
BOOL CreateEmpty();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla oluşturulursa sıfırsız; aksi takdirde 0.

## <a name="cpictureholdercreatefrombitmap"></a><a name="createfrombitmap"></a>CPictureHolder::CreateFromBitmap

Resim nesnesini bir 'deki başlangıç `CPictureHolder`olarak almak için bir bit eşlemi kullanır.

```
BOOL CreateFromBitmap(
    UINT idResource);

BOOL CreateFromBitmap(
    CBitmap* pBitmap,
    CPalette* pPal = NULL,
    BOOL bTransferOwnership = TRUE);

BOOL CreateFromBitmap(
    HBITMAP hbm,
    HPALETTE hpal = NULL,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>Parametreler

*idResource*<br/>
Bitmap kaynağının kaynak kimliği.

*pBitmap*<br/>
[CBitmap](../../mfc/reference/cbitmap-class.md) nesnesine işaretçi.

*pPal*<br/>
[CPalette](../../mfc/reference/cpalette-class.md) nesnesine işaretçi.

*bTransferOwnership*<br/>
Resim nesnesinin bit eşlemi ve palet nesnelerinin sahipliğini alıp almayacağını gösterir.

*Hbm*<br/>
`CPictureHolder` Nesnenin oluşturulduğu bit eşlenere işle.

*hpal*<br/>
Bit eşlemi işlemek için kullanılan palete işle.

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla oluşturulursa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*bTransferOwnership* TRUE ise, arayan bu çağrı döndükten sonra bit eşlemi veya palet nesnesini herhangi bir şekilde kullanmamalıdır. *bTransferOwnership* FALSE ise, arayan bit eşlemi ve palet nesnelerinin resim nesnesinin ömrü boyunca geçerli kalmasını sağlamaktan sorumludur.

## <a name="cpictureholdercreatefromicon"></a><a name="createfromicon"></a>CPictureHolder::CreateFromIcon

Resim nesnesini bir 'de başlatmak için bir `CPictureHolder`simge kullanır.

```
BOOL CreateFromIcon(
    UINT idResource);

BOOL CreateFromIcon(
    HICON hIcon,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>Parametreler

*idResource*<br/>
Bitmap kaynağının kaynak kimliği.

*Hıcon*<br/>
Nesnenin oluşturulduğu simgeye `CPictureHolder` işleyin.

*bTransferOwnership*<br/>
Resim nesnesinin simge nesnesinin sahipliğini alıp almayacağını gösterir.

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla oluşturulursa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*bTransferOwnership* TRUE ise, arayan bu çağrı döndükten sonra simge nesnesini hiçbir şekilde kullanmamalıdır. *bTransferOwnership* FALSE ise, arayan simge nesnesinin resim nesnesinin ömrü boyunca geçerli kalmasını sağlamaktan sorumludur.

## <a name="cpictureholdercreatefrommetafile"></a><a name="createfrommetafile"></a>CPictureHolder::CreateFromMetafile

Resim nesnesini bir `CPictureHolder`'de başlatmak için bir metadosya kullanır.

```
BOOL CreateFromMetafile(
    HMETAFILE hmf,
    int xExt,
    int yExt,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>Parametreler

*hmf*<br/>
Nesneyi oluşturmak için kullanılan `CPictureHolder` metadosyaya işle.

*xExt*<br/>
Resmin X ölçüde.

*yExt*<br/>
Resmin Y kapsamı.

*bTransferOwnership*<br/>
Resim nesnesinin metadosya nesnesinin sahipliğini alıp almayacağını gösterir.

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla oluşturulursa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*bTransferOwnership* TRUE ise, arayan bu çağrı döndükten sonra metadosya nesnesini herhangi bir şekilde kullanmamalıdır. *bTransferOwnership* FALSE ise, arayan metadosya nesnesinin resim nesnesinin ömrü boyunca geçerli kalmasını sağlamaktan sorumludur.

## <a name="cpictureholdergetdisplaystring"></a><a name="getdisplaystring"></a>CPictureHolder::GetDisplayString

Kapsayıcının özellik tarayıcısında görüntülenen dizeyi alır.

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>Parametreler

*strValue*<br/>
Ekran dizesini tutmak için [CString'e](../../atl-mfc-shared/reference/cstringt-class.md) başvuru.

### <a name="return-value"></a>Dönüş Değeri

Dize başarıyla alınırsa sıfırsız; aksi takdirde 0.

## <a name="cpictureholdergetpicturedispatch"></a><a name="getpicturedispatch"></a>CPictureHolder::GetPictureDispatch

Bu işlev nesnenin `CPictureHolder` `IPictureDisp` arabirimine bir işaretçi döndürür.

```
LPPICTUREDISP GetPictureDispatch();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin `CPictureHolder` `IPictureDisp` arabirimine işaretçi.

### <a name="remarks"></a>Açıklamalar

Arayan, bu `Release` işaretçiyi bitirdiğinde bu işaretçiyi aramalıdır.

## <a name="cpictureholdergettype"></a><a name="gettype"></a>CPictureHolder::GetType

Resmin bitmap, metadosya veya simge olup olmadığını gösterir.

```
short GetType();
```

### <a name="return-value"></a>Dönüş Değeri

Resmin türünü gösteren bir değer. Olası değerler ve anlamları aşağıdaki gibidir:

|Değer|Anlamı|
|-----------|-------------|
|PICTYPE_UNINITIALIZED|`CPictureHolder`nesne birleştiricidir.|
|PICTYPE_NONE|`CPictureHolder`nesne boştur.|
|PICTYPE_BITMAP|Resim bir bitmap olduğunu.|
|PICTYPE_METAFILE|Resim bir metadosyadır.|
|PICTYPE_ICON|Resim bir simgedir.|

## <a name="cpictureholderm_ppict"></a><a name="m_ppict"></a>CPictureHolder::m_pPict

Nesnenin `CPictureHolder` `IPicture` arabirimine işaretçi.

```
LPPICTURE m_pPict;
```

## <a name="cpictureholderrender"></a><a name="render"></a>CPictureHolder::Render

*Resmi rcRender*tarafından başvurulan dikdörtgende işler.

```cpp
void Render(
    CDC* pDC,
    const CRect& rcRender,
    const CRect& rcWBounds);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Resmin oluşturulmak üzere görüntübağlamını işaretle.

*rcRender*<br/>
Resmin oluşturulabilmek için dikdörtgen.

*rcWBounds*<br/>
Resmi oluşturan nesnenin sınırlayıcı dikdörtgenini temsil eden dikdörtgen. Bir denetim için, bu dikdörtgen COleControl bir geçersiz kılma geçirilen *rcBounds* [parametresi::OnDraw](../../mfc/reference/colecontrol-class.md#ondraw).

## <a name="cpictureholdersetpicturedispatch"></a><a name="setpicturedispatch"></a>CPictureHolder::SetPictureDispatch

Nesneyi `CPictureHolder` bir `IPictureDisp` arabirime bağlar.

```cpp
void SetPictureDispatch(LPPICTUREDISP pDisp);
```

### <a name="parameters"></a>Parametreler

*pDisp*<br/>
Yeni `IPictureDisp` arabirimi işaretçi.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Cfontholder Sınıfı](../../mfc/reference/cfontholder-class.md)
