---
title: CBitmap sınıfı
ms.date: 11/04/2016
f1_keywords:
- CBitmap
- AFXWIN/CBitmap
- AFXWIN/CBitmap::CBitmap
- AFXWIN/CBitmap::CreateBitmap
- AFXWIN/CBitmap::CreateBitmapIndirect
- AFXWIN/CBitmap::CreateCompatibleBitmap
- AFXWIN/CBitmap::CreateDiscardableBitmap
- AFXWIN/CBitmap::FromHandle
- AFXWIN/CBitmap::GetBitmap
- AFXWIN/CBitmap::GetBitmapBits
- AFXWIN/CBitmap::GetBitmapDimension
- AFXWIN/CBitmap::LoadBitmap
- AFXWIN/CBitmap::LoadMappedBitmap
- AFXWIN/CBitmap::LoadOEMBitmap
- AFXWIN/CBitmap::SetBitmapBits
- AFXWIN/CBitmap::SetBitmapDimension
helpviewer_keywords:
- CBitmap [MFC], CBitmap
- CBitmap [MFC], CreateBitmap
- CBitmap [MFC], CreateBitmapIndirect
- CBitmap [MFC], CreateCompatibleBitmap
- CBitmap [MFC], CreateDiscardableBitmap
- CBitmap [MFC], FromHandle
- CBitmap [MFC], GetBitmap
- CBitmap [MFC], GetBitmapBits
- CBitmap [MFC], GetBitmapDimension
- CBitmap [MFC], LoadBitmap
- CBitmap [MFC], LoadMappedBitmap
- CBitmap [MFC], LoadOEMBitmap
- CBitmap [MFC], SetBitmapBits
- CBitmap [MFC], SetBitmapDimension
ms.assetid: 3980616a-c59d-495a-86e6-62bd3889c84c
ms.openlocfilehash: 6722011bf343a391fcc7180558eead5c039afc59
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53178180"
---
# <a name="cbitmap-class"></a>CBitmap sınıfı

Bir Windows grafik cihaz arabirimi (GDI) bit eşlemi kapsüller ve bit eşlemi yönlendirmek üzere öğe işlevleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CBitmap : public CGdiObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CBitmap::CBitmap](#cbitmap)|Oluşturur bir `CBitmap` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CBitmap::CreateBitmap](#createbitmap)|Belirtilen genişlik, yükseklik ve desen bit olan bir cihaza bağlı bellek bit eşlem nesnesiyle başlatır.|
|[CBitmap::CreateBitmapIndirect](#createbitmapindirect)|Verilen nesne bir bit eşlem genişlik, yükseklik ve (belirtilmişse) bit deseni ile başlatır bir `BITMAP` yapısı.|
|[CBitmap::CreateCompatibleBitmap](#createcompatiblebitmap)|Böylece belirtilen bir cihaz ile uyumlu bir bit eşlem nesnesiyle başlatır.|
|[CBitmap::CreateDiscardableBitmap](#creatediscardablebitmap)|Belirtilen bir cihaz ile uyumlu olan discardable bir bit eşlem nesnesiyle başlatır.|
|[CBitmap::FromHandle](#fromhandle)|Bir işaretçi döndüren bir `CBitmap` nesnesi bir işleyici için bir Windows verildiğinde `HBITMAP` bit eşlem.|
|[CBitmap::GetBitmap](#getbitmap)|Dolduran bir `BITMAP` yapısı bit eşlem hakkında bilgi.|
|[CBitmap::GetBitmapBits](#getbitmapbits)|Belirtilen bit eşlem bitleri belirtilen arabelleğe kopyalar.|
|[CBitmap::GetBitmapDimension](#getbitmapdimension)|Genişlik ve yükseklik bit eşlemin döndürür. Yükseklik ve genişlik daha önce ayarlanan kabul edilir [SetBitmapDimension](#setbitmapdimension) üye işlevi.|
|[CBitmap::LoadBitmap](#loadbitmap)|Bit eşlem nesnesine ekleniyor ve adlandırılmış bit eşlemi Kaynak yüklenen uygulamanın yürütülebilir dosya tarafından nesnesini başlatır.|
|[CBitmap::LoadMappedBitmap](#loadmappedbitmap)|Bir bit eşlemi yükleyen ve geçerli sistem renkleri için renk eşler.|
|[CBitmap::LoadOEMBitmap](#loadoembitmap)|Önceden tanımlanmış bir Windows bit eşlem yükleniyor ve bit eşlem nesnesine ekleniyor nesnesini başlatır.|
|[CBitmap::SetBitmapBits](#setbitmapbits)|Bir bit eşlem bitleri için belirtilen bit değerleri ayarlar.|
|[CBitmap::SetBitmapDimension](#setbitmapdimension)|Genişlik ve yükseklik bir bit eşlem 0,1 milimetre birimlerindeki atar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[HBITMAP CBitmap::operator](#operator_hbitmap)|Bağlı Windows tanıtıcısını döndürür `CBitmap` nesne.|

## <a name="remarks"></a>Açıklamalar

Kullanılacak bir `CBitmap` nesnesi, nesne oluşturmak, başlatma üye işlevleri biriyle bir bit eşlem tanıtıcı eklemek ve sonra nesnenin üye işlevlerini çağırın.

Grafik nesneler gibi kullanma hakkında daha fazla bilgi için `CBitmap`, bkz: [grafik nesneleri](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CBitmap`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="cbitmap"></a>  CBitmap::CBitmap

Oluşturur bir `CBitmap` nesne.

```
CBitmap();
```

### <a name="remarks"></a>Açıklamalar

Elde edilen nesnenin başlatma üye işlevleri ile başlatılmalıdır.

##  <a name="createbitmap"></a>  CBitmap::CreateBitmap

Belirtilen genişlik, yükseklik ve bit desenine sahip bir cihaza bağlı bellek bit eşlem başlatır.

```
BOOL CreateBitmap(
    int nWidth,
    int nHeight,
    UINT nPlanes,
    UINT nBitcount,
    const void* lpBits);
```

### <a name="parameters"></a>Parametreler

*nWidth*<br/>
Bit eşlem genişliği (piksel cinsinden) belirtir.

*nHeight*<br/>
Bit eşlem (piksel cinsinden) yüksekliğini belirtir.

*nPlanes*<br/>
Renk düzlemi sayısı bit eşleminde belirtir.

*nBitcount*<br/>
Görüntü piksel başına renk bit sayısını belirtir.

*lpBits*<br/>
İlk bit eşlem bit değerleri içeren bir bayt dizisi işaret. NULL ise, yeni bir bit eşlem bırakılır başlatılmamış.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

İçin bir renk bit eşlem ya da *nPlanes* veya *nBitcount* parametresi 1 olarak ayarlanmalıdır. Bu parametrelerin her ikisini de 1 olarak ayarlarsanız `CreateBitmap` tek renkli bir bit eşlem oluşturur.

Bir bit eşlem doğrudan görüntüleme cihazı için seçilemez olsa da, bunu bir "bellek cihaz bağlamı" için geçerli bit eşlem olarak kullanarak seçilebilir [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) ve kullanaraktümuyumlucihazbağlamınakopyalanan[CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) işlevi.

Bitirdiğinizde ile `CBitmap` tarafından oluşturulan nesne `CreateBitmap` işlev, ilk cihaz bağlamı dışında bir bit eşlem seçin ve ardından silme `CBitmap` nesne.

Daha fazla bilgi için açıklamasına bakın `bmBits` alanındaki `BITMAP` yapısı. [Bit eşlem](/windows/desktop/api/wingdi/ns-wingdi-tagbitmap) yapısı altında açıklanan [CBitmap::CreateBitmapIndirect](#createbitmapindirect) üye işlevi.

##  <a name="createbitmapindirect"></a>  CBitmap::CreateBitmapIndirect

Genişlik, yükseklik ve işaret ettiği yapısı verilen (belirtilmişse) bit desenine sahip bir bit eşlem başlatır *lpBitmap*.

```
BOOL CreateBitmapIndirect(LPBITMAP lpBitmap);
```

### <a name="parameters"></a>Parametreler

*lpBitmap*<br/>
İşaret eden bir [bit eşlem](/windows/desktop/api/wingdi/ns-wingdi-tagbitmap) bit eşlem hakkında bilgi içeren yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir bit eşlem doğrudan görüntüleme cihazı için seçilemez ancak, bir bellek cihaz bağlamı için geçerli bit eşlem olarak kullanarak seçilebilir [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) ve kullanaraktümuyumlucihazbağlamınakopyalanan[CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) veya [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) işlevi. ( [CDC::PatBlt](../../mfc/reference/cdc-class.md#patblt) işlevi, doğrudan görünen cihaz bağlamı için geçerli fırça için bit eşlem kopyalayabilir.)

Varsa `BITMAP` yapısı tarafından işaret edilen *lpBitmap* parametresi doldurulur kullanarak `GetObject` işlevi, bit eşlem bitleri belirtilmedi ve bit eşlem başlatılmadı. Bit eşlem başlatmak için bir uygulama bir işlev gibi kullanabilirsiniz [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) veya [SetDIBits](/windows/desktop/api/wingdi/nf-wingdi-setdibits) ilk parametresi tarafından belirtilen bit eşlem bitleri kopyalanacak `CGdiObject::GetObject` göre oluşturulan bit eşlemi `CreateBitmapIndirect`.

Bitirdiğinizde ile `CBitmap` ile oluşturulan nesne `CreateBitmapIndirect` işlev, ilk cihaz bağlamı dışında bir bit eşlem seçin ve ardından silme `CBitmap` nesne.

##  <a name="createcompatiblebitmap"></a>  CBitmap::CreateCompatibleBitmap

Tarafından belirtilen cihaz ile uyumlu bir bit eşlem başlatır *pDC*.

```
BOOL CreateCompatibleBitmap(
    CDC* pDC,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Cihaz bağlamını belirtir.

*nWidth*<br/>
Bit eşlem genişliği (piksel cinsinden) belirtir.

*nHeight*<br/>
Bit eşlem (piksel cinsinden) yüksekliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bit eşlem renk düzlemleri aynı sayıda veya belirtilen bir cihaz bağlamı aynı piksel başına bit biçimi vardır. Geçerli bir bit eşlem ile belirtilen ile uyumlu olan herhangi bir bellek aygıt olarak seçilebilir *pDC*.

Varsa *pDC* bir bellek cihaz bağlamı döndürülen bir bit eşlem bu cihaz bağlamında seçili bit eşlem aynı biçimi vardır. "Bellek cihaz bağlamı" görüntü yüzeyini temsil eden bellek bloğudur. Uyumlu cihaz gerçek görüntü yüzeyine kopyalamadan önce bellekte resimler hazırlamak için kullanılabilir.

Bir bellek cihaz bağlamı oluşturulduğunda, GDI stok tek renkli bir bit eşlem için otomatik olarak seçer.

Bir renk bellek cihaz bağlamı rengi ya da seçili tek renkli bir bit eşlemler olabileceğinden, bit eşlem biçimi tarafından döndürülen `CreateCompatibleBitmap` işlevi her zaman aynı değildir; ancak, bir nonmemory cihaz bağlamı için uyumlu bir bit eşlem biçimi her zaman içinde cihaz biçimi.

Bitirdiğinizde ile `CBitmap` ile oluşturulan nesne `CreateCompatibleBitmap` işlev, ilk cihaz bağlamı dışında bir bit eşlem seçin ve ardından silme `CBitmap` nesne.

##  <a name="creatediscardablebitmap"></a>  CBitmap::CreateDiscardableBitmap

Tarafından tanımlanan cihaz bağlamı ile uyumlu olan discardable bir bit eşlem başlatır *pDC*.

```
BOOL CreateDiscardableBitmap(
    CDC* pDC,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Bir cihaz bağlamını belirtir.

*nWidth*<br/>
Bit eşlem (BITS) genişliğini belirtir.

*nHeight*<br/>
Bit eşlem (BITS) yüksekliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bit eşlem renk düzlemleri aynı sayıda veya belirtilen bir cihaz bağlamı aynı piksel başına bit biçimi vardır. Bir uygulama tarafından belirtilen ile uyumlu bir bellek cihazının geçerli bit eşlem olarak bu bit eşlem seçin *pDC*.

Windows, yalnızca uygulamanın bunu bir ekran bağlamına seçmemişse, bu işlev tarafından oluşturulan bir bit eşlem atabilirsiniz. Seçili ve uygulamayı daha sonra seçmek dener Windows bit eşlem atar, [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) işlev NULL döndürür.

Bitirdiğinizde ile `CBitmap` ile oluşturulan nesne `CreateDiscardableBitmap` işlev, ilk cihaz bağlamı dışında bir bit eşlem seçin ve ardından silme `CBitmap` nesne.

##  <a name="fromhandle"></a>  CBitmap::FromHandle

Bir işaretçi döndüren bir `CBitmap` nesnesi bir işleyici Windows GDI bit eşleme verildiğinde.

```
static CBitmap* PASCAL FromHandle(HBITMAP hBitmap);
```

### <a name="parameters"></a>Parametreler

*Hbıtmap*<br/>
GDI Windows bit eşlem belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `CBitmap` nesne başarılı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Varsa bir `CBitmap` nesne zaten iliştirilmemiş tanıtıcı, geçici bir `CBitmap` nesnesi oluşturulur ve bağlı. Bu geçici `CBitmap` tüm geçici grafik, zaman sonraki açışınızda uygulama boşta kalma süresi kendi olay döngüsü olana kadar nesneler silinir yalnızca nesne geçerlidir. Bunu belirten bir başka yolu geçici bir nesne yalnızca bir pencere iletisi işlenirken geçerli olmasıdır.

##  <a name="getbitmap"></a>  CBitmap::GetBitmap

Ekli eşlemiyle görüntü özelliklerini alır.

```
int GetBitmap(BITMAP* pBitMap);
```

### <a name="parameters"></a>Parametreler

*pBitMap*<br/>
İşaretçi bir [bit eşlem](/windows/desktop/api/wingdi/ns-wingdi-tagbitmap) yapısı görüntü özelliklerini alır. Bu parametre NULL olmamalıdır.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

##  <a name="getbitmapbits"></a>  CBitmap::GetBitmapBits

Ekli bit eşlem bit desenini belirtilen arabelleğe kopyalar.

```
DWORD GetBitmapBits(
    DWORD dwCount,
    LPVOID lpBits) const;
```

### <a name="parameters"></a>Parametreler

*dwCount*<br/>
Arabelleğe kopyalanacak bayt sayısı.

*lpBits*<br/>
Bit eşlem alacak arabellek için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa arabelleğe kopyalanan bayt sayısı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Kullanım [CBitmap::GetBitmap](#getbitmap) gerekli arabellek boyutunu belirlemek için.

##  <a name="getbitmapdimension"></a>  CBitmap::GetBitmapDimension

Genişlik ve yükseklik bit eşlemin döndürür.

```
CSize GetBitmapDimension() const;
```

### <a name="return-value"></a>Dönüş Değeri

Genişlik ve yükseklik bit eşlemin 0,1 milimetre birimleriyle ölçülür. Yükseklik bulunduğu `cy` üyesi `CSize` nesne ve genişliğini `cx` üyesi. Bit eşlem genişliği ve yüksekliği kullanarak ayarlanmamış ise `SetBitmapDimension`, dönüş değeri 0'dır.

### <a name="remarks"></a>Açıklamalar

Yükseklik ve genişlik kullanarak daha önce ayarlanan varsayılır [SetBitmapDimension](#setbitmapdimension) üye işlevi.

##  <a name="loadbitmap"></a>  CBitmap::LoadBitmap

Bit eşlem kaynağı tarafından adlandırılan yükler *lpszResourceName* veya kimlik numarası ile tanımlanan *nIDResource* uygulamanın yürütülebilir dosya.

```
BOOL LoadBitmap(LPCTSTR lpszResourceName);
BOOL LoadBitmap(UINT nIDResource);
```

### <a name="parameters"></a>Parametreler

*lpszResourceName*<br/>
Bit eşlem kaynağının adını içeren bir boş sonlandırılmış dizeye işaret eder.

*nIDResource*<br/>
Bit eşlem kaynağının kaynak kimliği numarasını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Yüklenen bit eşlem iliştirildiği `CBitmap` nesne.

Bit eşlem tarafından tanımladıysanız *lpszResourceName* yok ya da bit eşlem yüklemek için yeterli bellek varsa, işlev 0 döndürür.

Kullanabileceğiniz [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) işlevi, bit eşlem silmek için yüklenen tarafından `LoadBitmap` işlevi, veya `CBitmap` yok Edicisi nesneyi sizin için siler.

> [!CAUTION]
>  Nesne silmeden önce bir cihaz bağlamına seçili emin olun.

Aşağıdaki 3.1 ve sonraki Windows sürümleri için eklendi:

OBM_UPARRROWIOBM_DNARROWIOBM_RGARROWIOBM_LFARROWI

Bu bit eşlemler Windows sürümleri için cihaz sürücüleri, 3.0 ve eski bulunamadı. Bit eşlemler ve görünümlerini içeren bir görüntü tam listesi için Windows SDK'sı bakın.

##  <a name="loadmappedbitmap"></a>  CBitmap::LoadMappedBitmap

Bir bit eşlem yük ve geçerli sistem renkleri için renk eşlemek için bu üye işlevini çağırın.

```
BOOL LoadMappedBitmap(
    UINT nIDBitmap,
    UINT nFlags = 0,
    LPCOLORMAP lpColorMap = NULL,
    int nMapSize = 0);
```

### <a name="parameters"></a>Parametreler

*nIDBitmap*<br/>
Bit eşlem kaynağının kimliği.

*nFlags*<br/>
Bir bit eşlem bayrağı. Sıfır veya CMB_MASKED olabilir.

*lpColorMap*<br/>
Bir işaretçi bir `COLORMAP` bit eşlemler eşleştirmek için gereken renk bilgilerini içeren yapısı. Bu parametre NULL ise, işlev varsayılan renk eşlemi kullanır.

*nMapSize*<br/>
Renk haritalar sayısı tarafından işaret edilen *lpColorMap*.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `LoadMappedBitmap` düğmesi metindeki yaygın olarak kullanılan renkler eşler.

Eşlenen bir bit eşlem oluşturma hakkında daha fazla bilgi için bkz. Windows işlevi [CreateMappedBitmap](http://go.microsoft.com/fwlink/p/?linkid=230562) ve [COLORMAP](/windows/desktop/api/commctrl/ns-commctrl-_colormap) Windows SDK'sındaki yapısı.

##  <a name="loadoembitmap"></a>  CBitmap::LoadOEMBitmap

Windows tarafından kullanılan önceden tanımlanmış bir bit eşlem yükler.

```
BOOL LoadOEMBitmap(UINT nIDBitmap);
```

### <a name="parameters"></a>Parametreler

*nIDBitmap*<br/>
Önceden tanımlanmış Windows bit eşlem kimliği sayısı. Olası değerler varsayılan olarak, WINDOWS aşağıda listelenmiştir. Y:

|||
|-|-|
|OBM_BTNCORNERS|OBM_OLD_RESTORE|
|OBM_BTSIZE|OBM_OLD_RGARROW|
|OBM_CHECK|OBM_OLD_UPARROW|
|OBM_CHECKBOXES|OBM_OLD_ZOOM|
|OBM_CLOSE|OBM_REDUCE|
|OBM_COMBO|OBM_REDUCED|
|OBM_DNARROW|OBM_RESTORE|
|OBM_DNARROWD|OBM_RESTORED|
|OBM_DNARROWI|OBM_RGARROW|
|OBM_LFARROW|OBM_RGARROWD|
|OBM_LFARROWD|OBM_RGARROWI|
|OBM_LFARROWI|OBM_SIZE|
|OBM_MNARROW|OBM_UPARROW|
|OBM_OLD_CLOSE|OBM_UPARROWD|
|OBM_OLD_DNARROW|OBM_UPARROW|
|OBM_OLD_LFARROW|OBM_ZOOM|
|OBM_OLD_REDUCE|OBM_ZOOMD|

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bit eşlem adları OBM_OLD ile başlayan Windows sürümlerinde 3.0 tarafından kullanılan bit eşlemleri temsil eder.

Sabit OEMRESOURCE WINDOWS eklemeden önce tanımlanmalıdır unutmayın. Herhangi birini kullanmak için H **OBM_** sabitler.

##  <a name="operator_hbitmap"></a>  HBITMAP CBitmap::operator

Ekli Windows GDI tanıtıcısını almak için bu işleci kullanın `CBitmap` nesne.

```
operator HBITMAP() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı, Windows GDI nesnesi için bir tanıtıcı tarafından temsil edilen varsa `CBitmap` nesne; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Doğrudan kullanılmasını desteklediği bir yayım işleciyle Bu işlecin olduğu bir `HBITMAP` nesne.

Grafik nesneler kullanma hakkında daha fazla bilgi için bkz. [grafik nesneleri](/windows/desktop/gdi/graphic-objects) Windows SDK.

##  <a name="setbitmapbits"></a>  CBitmap::SetBitmapBits

Bir bit eşlem bitleri tarafından verilen bit değerleri ayarlar *lpBits*.

```
DWORD SetBitmapBits(
    DWORD dwCount,
    const void* lpBits);
```

### <a name="parameters"></a>Parametreler

*dwCount*<br/>
İşaret ettiği bayt sayısını belirtir *lpBits*.

*lpBits*<br/>
İşaret kopyalanacağı piksel değerleri içeren bir bayt dizisine `CBitmap` nesne. İçin bit eşlem görüntüsünü doğru şekilde işlemek sırada CBitmap örneğinin oluşturulduğu belirtilmiş yükseklik, genişlik ve renk derinliği değerleri için uygun değerleri biçimlendirilmelidir. Daha fazla bilgi için [CBitmap::CreateBitmap](#createbitmap).

### <a name="return-value"></a>Dönüş Değeri

Bit eşlem bitleri kurulmasına bayt sayısı; işlev başarısız olursa 0.

##  <a name="setbitmapdimension"></a>  CBitmap::SetBitmapDimension

Genişlik ve yükseklik bir bit eşlem 0,1 milimetre birimlerindeki atar.

```
CSize SetBitmapDimension(
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>Parametreler

*nWidth*<br/>
Bit eşlem (birimlerindeki 0,1 milimetre) genişliğini belirtir.

*nHeight*<br/>
Bit eşlem (birimlerindeki 0,1 milimetre) yüksekliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Önceki bit eşlem boyutları. Yükseklik konusu `cy` üye değişkeninin `CSize` nesne ve genişlik `cx` üye değişkeni.

### <a name="remarks"></a>Açıklamalar

Bir uygulama çağırdığında dışında döndürmek üzere bu değerleri GDI kullanmaz [GetBitmapDimension](#getbitmapdimension) üye işlevi.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek MDI](../../visual-cpp-samples.md)<br/>
[CGdiObject Sınıfı](../../mfc/reference/cgdiobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

