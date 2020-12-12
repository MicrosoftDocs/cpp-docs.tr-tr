---
description: 'Daha fazla bilgi edinin: Cpictureş sınıfı'
title: Cpictureş sınıfı
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
ms.openlocfilehash: 47eacb66191e21b300aaa0d06bc23155fabaf651
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301483"
---
# <a name="cpictureholder-class"></a>Cpictureş sınıfı

Kullanıcının denetiinizdeki bir resmi görüntülemesine izin veren bir Picture özelliği uygular.

## <a name="syntax"></a>Syntax

```
class CPictureHolder
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cpictureş:: Cpicturetutucusu](#cpictureholder)|Bir `CPictureHolder` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cpictureş:: CreateEmpty](#createempty)|Boş bir `CPictureHolder` nesne oluşturur.|
|[Cpictureş:: CreateFromBitmap](#createfrombitmap)|`CPictureHolder`Bit eşlemden bir nesne oluşturur.|
|[Cpictureş:: CreateFromIcon](#createfromicon)|`CPictureHolder`Bir simgeden bir nesne oluşturur.|
|[Cpictureş:: CreateFromMetafile](#createfrommetafile)|`CPictureHolder`Meta dosyasından bir nesne oluşturur.|
|[Cpictureş:: GetDisplayString](#getdisplaystring)|Denetim kapsayıcısının özellik tarayıcısında görünen dizeyi alır.|
|[Cpictureş:: GetPictureDispatch](#getpicturedispatch)|`CPictureHolder`Nesnenin `IDispatch` arabirimini döndürür.|
|[Cpictureş:: GetType](#gettype)|`CPictureHolder`Nesnenin bit eşlem, meta dosyası veya simge olduğunu söyler.|
|[Cpictureş:: Render](#render)|Resmi işler.|
|[Cpictureş:: SetPictureDispatch](#setpicturedispatch)|`CPictureHolder`Nesnenin `IDispatch` arabirimini ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Cpictureş:: m_pPict](#m_ppict)|Resim nesnesine yönelik bir işaretçi.|

## <a name="remarks"></a>Açıklamalar

`CPictureHolder` taban sınıfına sahip değildir.

Hisse senedi resmi özelliği ile geliştirici, ekran için bir bit eşlem, simge veya meta dosya belirtebilir.

Özel resim özellikleri oluşturma hakkında daha fazla bilgi için [MFC ActiveX denetimleri: ActiveX denetiminde resim kullanma](../../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CPictureHolder`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxctl. h

## <a name="cpictureholdercpictureholder"></a><a name="cpictureholder"></a> Cpictureş:: Cpicturetutucusu

Bir `CPictureHolder` nesnesi oluşturur.

```
CPictureHolder();
```

## <a name="cpictureholdercreateempty"></a><a name="createempty"></a> Cpictureş:: CreateEmpty

Boş bir `CPictureHolder` nesne oluşturur ve bunu bir arabirime bağlar `IPicture` .

```
BOOL CreateEmpty();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla oluşturulduysa sıfır dışı; Aksi takdirde 0.

## <a name="cpictureholdercreatefrombitmap"></a><a name="createfrombitmap"></a> Cpictureş:: CreateFromBitmap

İçindeki resim nesnesini başlatmak için bir bit eşlem kullanır `CPictureHolder` .

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

*ıdresource*<br/>
Bir bit eşlem kaynağının kaynak KIMLIĞI.

*Pbımap*<br/>
[CBitmap](../../mfc/reference/cbitmap-class.md) nesnesine yönelik işaretçi.

*pPal*<br/>
[CPalette](../../mfc/reference/cpalette-class.md) nesnesine yönelik işaretçi.

*Btransfersahiplik*<br/>
Resim nesnesinin bit eşlem ve palet nesneleri sahipliğini alıp etmeyeceğini belirtir.

*HBM*<br/>
Nesnenin oluşturulduğu bit eşlem için tanıtıcı `CPictureHolder` .

*hpal*<br/>
Bit eşlemi işlemek için kullanılan paleti işleme.

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla oluşturulduysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*Btransfersahiplik* true ise, çağıran, bu çağrı geri çağrıldıktan sonra herhangi bir şekilde bit eşlem veya palet nesnesini kullanmamalıdır. *Btransfersahiplik* false ise, çağıran, resim nesnesinin kullanım ömrü boyunca bit eşlem ve palet nesnelerinin geçerli kalmasını sağlamaktan sorumludur.

## <a name="cpictureholdercreatefromicon"></a><a name="createfromicon"></a> Cpictureş:: CreateFromIcon

İçindeki resim nesnesini başlatmak için bir simge kullanır `CPictureHolder` .

```
BOOL CreateFromIcon(
    UINT idResource);

BOOL CreateFromIcon(
    HICON hIcon,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>Parametreler

*ıdresource*<br/>
Bir bit eşlem kaynağının kaynak KIMLIĞI.

*HICON*<br/>
Nesnenin oluşturulduğu simgeye yönelik işleyici `CPictureHolder` .

*Btransfersahiplik*<br/>
Resim nesnesinin simge nesnesinin sahipliğini alıp etmeyeceğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla oluşturulduysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*Btransfersahiplik* true ise, çağıran, bu çağrı geri çağrıldıktan sonra herhangi bir şekilde Icon nesnesini kullanmamalıdır. *Btransfersahiplik* false ise, çağıran, simge nesnesinin resim nesnesinin kullanım ömrü boyunca geçerli kalmasını sağlamaktan sorumludur.

## <a name="cpictureholdercreatefrommetafile"></a><a name="createfrommetafile"></a> Cpictureş:: CreateFromMetafile

Bir meta dosyası kullanarak resim nesnesini ' de başlatır `CPictureHolder` .

```
BOOL CreateFromMetafile(
    HMETAFILE hmf,
    int xExt,
    int yExt,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>Parametreler

*HMF*<br/>
Nesneyi oluşturmak için kullanılan meta dosyası için tanıtıcı `CPictureHolder` .

*xExt*<br/>
Resmin X uzantısı.

*yıln*<br/>
Resmin Y uzantısı.

*Btransfersahiplik*<br/>
Resim nesnesinin meta dosya nesnesinin sahipliğini alıp etmeyeceğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla oluşturulduysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*Btransfersahiplik* true ise, çağıran, bu çağrı geri çağrıldıktan sonra herhangi bir şekilde meta dosyası nesnesini kullanmamalıdır. *Btransfersahiplik* yanlış ise, dosya kümesi nesnesinin resim nesnesinin kullanım ömrü boyunca geçerli kalmasını sağlamaktan sorumludur.

## <a name="cpictureholdergetdisplaystring"></a><a name="getdisplaystring"></a> Cpictureş:: GetDisplayString

Kapsayıcının özellik tarayıcısında görüntülenen dizeyi alır.

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>Parametreler

*strValue*<br/>
Görüntüleme dizesini tutan [CString](../../atl-mfc-shared/reference/cstringt-class.md) başvurusu.

### <a name="return-value"></a>Dönüş Değeri

Dize başarıyla alınırsa sıfır dışı; Aksi takdirde 0.

## <a name="cpictureholdergetpicturedispatch"></a><a name="getpicturedispatch"></a> Cpictureş:: GetPictureDispatch

Bu işlev, nesnenin arabirimine bir işaretçi döndürür `CPictureHolder` `IPictureDisp` .

```
LPPICTUREDISP GetPictureDispatch();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin arabirimine yönelik bir işaretçi `CPictureHolder` `IPictureDisp` .

### <a name="remarks"></a>Açıklamalar

Çağıran, `Release` ile işiniz bittiğinde bu işaretçiye çağrı sağlamalıdır.

## <a name="cpictureholdergettype"></a><a name="gettype"></a> Cpictureş:: GetType

Resmin bir bit eşlem, meta dosya veya simge olduğunu gösterir.

```
short GetType();
```

### <a name="return-value"></a>Dönüş Değeri

Resmin türünü gösteren bir değer. Olası değerler ve anlamları aşağıdaki gibidir:

|Değer|Anlamı|
|-----------|-------------|
|PICTYPE_UNINITIALIZED|`CPictureHolder` nesne başlatılmadı.|
|PICTYPE_NONE|`CPictureHolder` nesne boş.|
|PICTYPE_BITMAP|Resim bir bit eşlemdir.|
|PICTYPE_METAFILE|Resim bir meta dosyası.|
|PICTYPE_ICON|Resim bir simgedir.|

## <a name="cpictureholderm_ppict"></a><a name="m_ppict"></a> Cpictureş:: m_pPict

Nesnenin arabirimine yönelik bir işaretçi `CPictureHolder` `IPicture` .

```
LPPICTURE m_pPict;
```

## <a name="cpictureholderrender"></a><a name="render"></a> Cpictureş:: Render

Resmi, *Rcrender* tarafından başvurulan dikdörtgende işler.

```cpp
void Render(
    CDC* pDC,
    const CRect& rcRender,
    const CRect& rcWBounds);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Resmin işlendiği görüntü bağlamına yönelik işaretçi.

*rcRender*<br/>
Resmin işlendiği dikdörtgen.

*Rcwsınır*<br/>
Resmi işleyen nesnenin sınırlayıcı dikdörtgenini temsil eden bir dikdörtgen. Bir denetim için bu dikdörtgen, [Coelcontrol:: OnDraw](../../mfc/reference/colecontrol-class.md#ondraw)geçersiz kılınmasına geçirilen *rcsınırlara* parametresidir.

## <a name="cpictureholdersetpicturedispatch"></a><a name="setpicturedispatch"></a> Cpictureş:: SetPictureDispatch

`CPictureHolder`Nesnesini bir `IPictureDisp` arabirime bağlar.

```cpp
void SetPictureDispatch(LPPICTUREDISP pDisp);
```

### <a name="parameters"></a>Parametreler

*pDisp*<br/>
Yeni arabirime yönelik işaretçi `IPictureDisp` .

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Cfontheski sınıfı](../../mfc/reference/cfontholder-class.md)
