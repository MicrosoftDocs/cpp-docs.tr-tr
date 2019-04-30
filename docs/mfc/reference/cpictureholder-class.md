---
title: CPictureHolder sınıfı
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
ms.openlocfilehash: 5386240114550826e4bf557b63310a91590afb55
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372887"
---
# <a name="cpictureholder-class"></a>CPictureHolder sınıfı

Kullanıcının sizin Denetiminizdeki bir resmi görüntülemek bir resim özelliği uygular.

## <a name="syntax"></a>Sözdizimi

```
class CPictureHolder
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPictureHolder::CPictureHolder](#cpictureholder)|Oluşturur bir `CPictureHolder` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPictureHolder::CreateEmpty](#createempty)|Boş bir `CPictureHolder` nesne.|
|[CPictureHolder::CreateFromBitmap](#createfrombitmap)|Oluşturur bir `CPictureHolder` nesneden bir bit eşlem.|
|[CPictureHolder::CreateFromIcon](#createfromicon)|Oluşturur bir `CPictureHolder` nesneden bir simge.|
|[CPictureHolder::CreateFromMetafile](#createfrommetafile)|Oluşturur bir `CPictureHolder` nesneden bir meta dosyası.|
|[CPictureHolder::GetDisplayString](#getdisplaystring)|Bir denetimi kapsayıcının özelliği tarayıcıda görüntülenen dizeyi alır.|
|[CPictureHolder::GetPictureDispatch](#getpicturedispatch)|Döndürür `CPictureHolder` nesnenin `IDispatch` arabirimi.|
|[CPictureHolder::GetType](#gettype)|Belirtir olup olmadığını `CPictureHolder` nesnedir bir bit eşlem, meta dosyası veya bir simge.|
|[CPictureHolder::Render](#render)|Resim işler.|
|[CPictureHolder::SetPictureDispatch](#setpicturedispatch)|Kümeleri `CPictureHolder` nesnenin `IDispatch` arabirimi.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CPictureHolder::m_pPict](#m_ppict)|Resim nesnesine bir işaretçi.|

## <a name="remarks"></a>Açıklamalar

`CPictureHolder` bir temel sınıfa sahip değil.

Stok resim özelliği ile bir bit eşlemi, simge veya görüntülemek için meta Geliştirici belirtebilirsiniz.

Özel Resim özellikleri oluşturma hakkında daha fazla bilgi için bkz [MFC ActiveX denetimleri: ActiveX denetiminde resim kullanma](../../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CPictureHolder`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxctl.h

##  <a name="cpictureholder"></a>  CPictureHolder::CPictureHolder

Oluşturur bir `CPictureHolder` nesne.

```
CPictureHolder();
```

##  <a name="createempty"></a>  CPictureHolder::CreateEmpty

Boş bir `CPictureHolder` nesne ve ona bağlanan bir `IPicture` arabirimi.

```
BOOL CreateEmpty();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla oluşturuldu olursa sıfır dışı; Aksi durumda 0.

##  <a name="createfrombitmap"></a>  CPictureHolder::CreateFromBitmap

Bir bit eşlem resmi nesneyi başlatmak için kullandığı bir `CPictureHolder`.

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
Bir bit eşlem kaynağının kaynak kimliği.

*pBitmap*<br/>
İşaretçi bir [CBitmap](../../mfc/reference/cbitmap-class.md) nesne.

*pPal*<br/>
İşaretçi bir [CPalette](../../mfc/reference/cpalette-class.md) nesne.

*bTransferOwnership*<br/>
Resim nesnesi bit eşlem ve palet nesneleri sahipliğini alıp almayacağını gösterir.

*hbm*<br/>
İşlemek için bit eşlem içinden `CPictureHolder` nesnesi oluşturulur.

*hpal*<br/>
Bit eşlem çizmek için kullanılan paletteki işleyin.

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla oluşturuldu olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsa *bTransferOwnership* doğru çağıran bir bit eşlem kullanmamanız gerekir veya palet nesne bu çağrı sonra herhangi bir şekilde döndürür. Varsa *bTransferOwnership* yanlış, bit eşlem ve palet nesneleri resim nesnesi ömrü boyunca geçerli kalmasını sağlamak için çağıran sorumludur.

##  <a name="createfromicon"></a>  CPictureHolder::CreateFromIcon

Resim nesneyi başlatmak için bir simge kullanan bir `CPictureHolder`.

```
BOOL CreateFromIcon(
    UINT idResource);

BOOL CreateFromIcon(
    HICON hIcon,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>Parametreler

*idResource*<br/>
Bir bit eşlem kaynağının kaynak kimliği.

*hIcon*<br/>
İşlemek için simge içinden `CPictureHolder` nesnesi oluşturulur.

*bTransferOwnership*<br/>
Resim nesnesi simgesi nesne sahipliğini alıp almayacağını gösterir.

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla oluşturuldu olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsa *bTransferOwnership* doğru ise, bu çağrı döndürdükten sonra çağıran simge nesnesi herhangi bir yolla kullanmamalısınız. Varsa *bTransferOwnership* yanlış, simge nesnesi Resim nesnesi ömrü boyunca geçerli kalmasını sağlamak için çağıran sorumludur.

##  <a name="createfrommetafile"></a>  CPictureHolder::CreateFromMetafile

Resim nesneyi başlatmak için bir meta dosyası kullanan bir `CPictureHolder`.

```
BOOL CreateFromMetafile(
    HMETAFILE hmf,
    int xExt,
    int yExt,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>Parametreler

*hmf*<br/>
Tanıtıcı oluşturmak için kullanılan meta `CPictureHolder` nesne.

*xExt*<br/>
Resim kapsamını x.

*yExt*<br/>
Resim kapsamını Y.

*bTransferOwnership*<br/>
Resim nesnesi meta dosyası nesne sahipliğini alıp almayacağını gösterir.

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla oluşturuldu olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsa *bTransferOwnership* doğru ise, bu çağrı döndürdükten sonra çağıran meta dosyası nesne herhangi bir yolla kullanmamalısınız. Varsa *bTransferOwnership* yanlış, çağıran, meta dosyası nesne Resim nesnesi ömrü boyunca geçerli kalır sağlamaktan sorumludur.

##  <a name="getdisplaystring"></a>  CPictureHolder::GetDisplayString

Bir kapsayıcının özelliği tarayıcıda görüntülenen dizeyi alır.

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>Parametreler

*strValue*<br/>
Başvuru [CString](../../atl-mfc-shared/reference/cstringt-class.md) görüntü dizesini tutacak olmasıdır.

### <a name="return-value"></a>Dönüş Değeri

Dize başarıyla aldı olursa sıfır dışı; Aksi durumda 0.

##  <a name="getpicturedispatch"></a>  CPictureHolder::GetPictureDispatch

Bu işlev, bir işaretçi döndürür. `CPictureHolder` nesnenin `IPictureDisp` arabirimi.

```
LPPICTUREDISP GetPictureDispatch();
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `CPictureHolder` nesnenin `IPictureDisp` arabirimi.

### <a name="remarks"></a>Açıklamalar

Çağıranın çağırmalıdır `Release` ile işiniz bittiğinde bu işaretçinin.

##  <a name="gettype"></a>  CPictureHolder::GetType

Resmi bir bit eşlem, meta dosyası veya simge olup olmadığını belirtir.

```
short GetType();
```

### <a name="return-value"></a>Dönüş Değeri

Resim türünü belirten bir değer. Olası değerler ve bunların anlamlarını açıklayan aşağıdaki gibidir:

|Değer|Açıklama|
|-----------|-------------|
|PICTYPE_UNINITIALIZED|`CPictureHolder` Nesne unititialized.|
|PICTYPE_NONE|`CPictureHolder` Nesne boştur.|
|PICTYPE_BITMAP|Bir bit eşlem resimdir.|
|PICTYPE_METAFILE|Resim meta dosyası bulunur.|
|PICTYPE_ICON|Resim, bir simge bulunur.|

##  <a name="m_ppict"></a>  CPictureHolder::m_pPict

Bir işaretçi `CPictureHolder` nesnenin `IPicture` arabirimi.

```
LPPICTURE m_pPict;
```

##  <a name="render"></a>  CPictureHolder::Render

Tarafından başvurulan dikdörtgen resim işler *rcRender*.

```
void Render(
    CDC* pDC,
    const CRect& rcRender,
    const CRect& rcWBounds);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
İşaretçi resmi işlenecek olan ekran içeriği.

*rcRender*<br/>
Dikdörtgen resim işlenecek olduğu.

*rcWBounds*<br/>
Dikdörtgen resim işleme nesnesinin temsil eden bir dikdörtgen. Bir denetim için olan bu dikdörtgenin *rcBounds* parametresi için geçersiz kılma geçirilmesi [COleControl::OnDraw](../../mfc/reference/colecontrol-class.md#ondraw).

##  <a name="setpicturedispatch"></a>  CPictureHolder::SetPictureDispatch

Bağlanan `CPictureHolder` nesnesini bir `IPictureDisp` arabirimi.

```
void SetPictureDispatch(LPPICTUREDISP pDisp);
```

### <a name="parameters"></a>Parametreler

*pDisp*<br/>
İşaretçi yeni `IPictureDisp` arabirimi.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFontHolder Sınıfı](../../mfc/reference/cfontholder-class.md)
