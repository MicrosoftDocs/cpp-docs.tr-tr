---
title: Cımage sınıfı
ms.date: 02/01/2018
f1_keywords:
- CImage
- ATLIMAGE/ATL::CImage
- ATLIMAGE/ATL::CImage::CImage
- ATLIMAGE/ATL::CImage::AlphaBlend
- ATLIMAGE/ATL::CImage::Attach
- ATLIMAGE/ATL::CImage::BitBlt
- ATLIMAGE/ATL::CImage::Create
- ATLIMAGE/ATL::CImage::CreateEx
- ATLIMAGE/ATL::CImage::Destroy
- ATLIMAGE/ATL::CImage::Detach
- ATLIMAGE/ATL::CImage::Draw
- ATLIMAGE/ATL::CImage::GetBits
- ATLIMAGE/ATL::CImage::GetBPP
- ATLIMAGE/ATL::CImage::GetColorTable
- ATLIMAGE/ATL::CImage::GetDC
- ATLIMAGE/ATL::CImage::GetExporterFilterString
- ATLIMAGE/ATL::CImage::GetHeight
- ATLIMAGE/ATL::CImage::GetImporterFilterString
- ATLIMAGE/ATL::CImage::GetMaxColorTableEntries
- ATLIMAGE/ATL::CImage::GetPitch
- ATLIMAGE/ATL::CImage::GetPixel
- ATLIMAGE/ATL::CImage::GetPixelAddress
- ATLIMAGE/ATL::CImage::GetTransparentColor
- ATLIMAGE/ATL::CImage::GetWidth
- ATLIMAGE/ATL::CImage::IsDIBSection
- ATLIMAGE/ATL::CImage::IsIndexed
- ATLIMAGE/ATL::CImage::IsNull
- ATLIMAGE/ATL::CImage::IsTransparencySupported
- ATLIMAGE/ATL::CImage::Load
- ATLIMAGE/ATL::CImage::LoadFromResource
- ATLIMAGE/ATL::CImage::MaskBlt
- ATLIMAGE/ATL::CImage::PlgBlt
- ATLIMAGE/ATL::CImage::ReleaseDC
- ATLIMAGE/ATL::CImage::ReleaseGDIPlus
- ATLIMAGE/ATL::CImage::Save
- ATLIMAGE/ATL::CImage::SetColorTable
- ATLIMAGE/ATL::CImage::SetPixel
- ATLIMAGE/ATL::CImage::SetPixelIndexed
- ATLIMAGE/ATL::CImage::SetPixelRGB
- ATLIMAGE/ATL::CImage::SetTransparentColor
- ATLIMAGE/ATL::CImage::StretchBlt
- ATLIMAGE/ATL::CImage::TransparentBlt
helpviewer_keywords:
- jpeg files
- bitmaps [C++], ATL and MFC support for
- images [C++], ATL and MFC support for
- gif files, ATL and MFC support
- .gif files, ATL and MFC support
- PNG files, ATL and MFC support
- CImage class
- transparent color
ms.assetid: 52861e3d-bf7e-481f-a240-90e88f76c490
ms.openlocfilehash: 0042fffb0eaa383909edd6647bcdb4375341d8dd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605861"
---
# <a name="cimage-class"></a>Cımage sınıfı

`CImage` Yük ve görüntüleri JPEG, BMP, GIF ve da Taşınabilir Ağ Grafikleri (PNG) biçimlerde kaydetme olanağı dahil olmak üzere Gelişmiş bit eşlem desteği sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CImage
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CImage::CImage](#cimage)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CImage::AlphaBlend](#alphablend)|Saydam veya yarı saydam fırçalarla piksel olan bit eşlemler görüntüler.|
|[CImage::Attach](#attach)|İçin bir HBITMAP bağlayan bir `CImage` nesne. DIB olmayan bölüm bit eşlemler veya DIB bölüm bit eşlemler ile kullanılabilir.|
|[CImage::BitBlt](#bitblt)|Bir bit eşlemi Kaynak cihaz bağlamında bu geçerli bir cihaz bağlamına kopyalar.|
|[CImage::Create](#create)|DIB bölümü olan bir bit eşlem oluşturur ve bunu daha önce oluşturulmuş ekler `CImage` nesne.|
|[CImage::CreateEx](#createex)|DIB bölüm bit eşlem (ile ek parametreler) oluşturur ve bunu daha önce oluşturulmuş ekler `CImage` nesne.|
|[CImage::Destroy](#destroy)|Bit eşlem ayırır `CImage` nesne ve bit eşlem yok eder.|
|[CImage::Detach](#detach)|Bit eşlem ayırır bir `CImage` nesne.|
|[CImage::Draw](#draw)|Bir bit eşlemi Kaynak dikdörtgenden hedef dikdörtgene kopyalar. `Draw` uzatır veya sıkıştırır gerekirse hedef dikdörtgenin boyutlarına uyacak şekilde bit eşlem ve alfa karıştırma ve saydam renkler işler.|
|[CImage::GetBits](#getbits)|Bit eşlem gerçek piksel değerleri için bir işaretçi alır.|
|[CImage::GetBPP](#getbpp)|Piksel başına bit alır.|
|[CImage::GetColorTable](#getcolortable)|Renkli Tablo girdileri aralığından kırmızı, yeşil, mavi (RGB) renk değerleri alır.|
|[CImage::GetDC](#getdc)|Geçerli bir bit eşlem içine seçili cihaz bağlamı alır.|
|[CImage::GetExporterFilterString](#getexporterfilterstring)|Mevcut görüntü biçimlerini ve açıklamalarının bulur.|
|[CImage::GetHeight](#getheight)|Geçerli görüntü piksel cinsinden yüksekliğini alır.|
|[CImage::GetImporterFilterString](#getimporterfilterstring)|Mevcut görüntü biçimlerini ve açıklamalarının bulur.|
|[CImage::GetMaxColorTableEntries](#getmaxcolortableentries)|Renkli Tablo girdileri maksimum sayısını alır.|
|[CImage::GetPitch](#getpitch)|Bayt cinsinden geçerli görüntünün aralığını alır.|
|[CImage::GetPixel](#getpixel)|Tarafından belirtilen piksel rengi alır *x* ve *y*.|
|[CImage::GetPixelAddress](#getpixeladdress)|Belirli bir pikselin adresini alır.|
|[CImage::GetTransparentColor](#gettransparentcolor)|Renk tablosunu saydam rengi konumunu alır.|
|[CImage::GetWidth](#getwidth)|Geçerli resmin piksel cinsinden genişliğini alır.|
|[CImage::IsDIBSection](#isdibsection)|Ekli bit eşlem DIB bölümü olup olmadığını belirler.|
|[CImage::IsIndexed](#isindexed)|Bir bit eşleşmemin rengi için dizinlenmiş palet eşlenmiş gösterir.|
|[CImage::IsNull](#isnull)|Bir kaynak bit eşlemi yüklü olmadığını gösterir.|
|[CImage::IsTransparencySupported](#istransparencysupported)|Uygulama saydam bit eşlemler destekleyip desteklemediğini belirtir.|
|[CImage::Load](#load)|Görüntüyü belirtilen dosyadan yükler.|
|[CImage::LoadFromResource](#loadfromresource)|Belirtilen kaynak görüntüyü yükler.|
|[CImage::MaskBlt](#maskblt)|Belirtilen maske ve ızgara işlemi kullanarak kaynak ve hedef bit eşlemler için renk verileri birleştirir.|
|[CImage::PlgBlt](#plgblt)|Bit bloğu aktarımı bir hedef cihaz bağlamında bir eğdiğinizde Paralel Kenar içine bir dikdörtgenden kaynak cihaz bağlamında gerçekleştirir.|
|[CImage::ReleaseDC](#releasedc)|Sürümleri ile alınan cihaz bağlamı [CImage::GetDC](#getdc).|
|[CImage::ReleaseGDIPlus](#releasegdiplus)|GDI +'TARAFINDAN kullanılan kaynakları serbest bırakır. Genel tarafından oluşturulan kaynakları serbest bırakmak için çağrılmalıdır `CImage` nesne.|
|[CImage::Save](#save)|Görüntüyü belirtilen tür olarak kaydeder. `Save` Görüntü seçenekleri belirtemezsiniz.|
|[CImage::SetColorTable](#setcolortable)|Kırmızı, yeşil, mavi RGB ayarlar) renk DIB bölümün rengi tablodaki girişleri aralığındaki değerler.|
|[CImage::SetPixel](#setpixel)|Belirtilen "rengin için" belirtilen koordinatlarda piksel ayarlar.|
|[CImage::SetPixelIndexed](#setpixelindexed)|Piksel renk paletinin belirtilen dizindeki belirtilen koordinatlarda ayarlar.|
|[CImage::SetPixelRGB](#setpixelrgb)|Belirtilen kırmızı, yeşil, mavi (RGB) değeri için belirtilen koordinatlarda piksel ayarlar.|
|[CImage::SetTransparentColor](#settransparentcolor)|Saydam olarak kabul edilmesi için renk dizinini ayarlar. Yalnızca bir renk paleti saydam olabilir.|
|[CImage::StretchBlt](#stretchblt)|Bir bit eşlemi Kaynak dikdörtgenden uzatma veya gerekirse, bit eşlemi hedef dikdörtgenin boyutlarına sıkıştırma bir hedef dikdörtgene kopyalar.|
|[CImage::TransparentBlt](#transparentblt)|Saydam renkli bir bit eşlemi Kaynak cihaz bağlamında bu geçerli bir cihaz bağlamına kopyalar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[HBITMAP CImage::operator](#operator_hbitmap)|Bağlı Windows tanıtıcısını döndürür `CImage` nesne.|

## <a name="remarks"></a>Açıklamalar

`CImage` veya herhangi bir CİHAZDAN bağımsız bit eşlem (DIB) bölümleri olan bit eşlemler kazanır. Ancak, kullanabileceğiniz [Oluştur](#create) veya [CImage::Load](#load) yalnızca DIB bölümleri ile. DIB olmayan bölüm bit eşleme ekleyebilirsiniz bir `CImage` kullanarak nesne [iliştirme](#attach), ancak daha sonra aşağıdaki kullanamazsınız `CImage` yalnızca DIB bölüm bit eşlemler destekleyen yöntemler:

- [GetBits](#getbits)

- [GetColorTable](#getcolortable)

- [GetMaxColorTableEntries](#getmaxcolortableentries)

- [GetPitch](#getpitch)

- [GetPixelAddress](#getpixeladdress)

- [IsIndexed](#isindexed)

- [SetColorTable](#setcolortable)

Ekli bir bit eşlem DIB bölümü olup olmadığını belirlemek için çağrı [IsDibSection](#isdibsection).

> [!NOTE]
> Visual Studio .NET 2003'te, bu sınıfın bir sayısını tutar `CImage` oluşturulan nesneler. Her sayısı ölçeklendirilinceye 0, işlev `GdiplusShutdown` GDI +'TARAFINDAN kullanılan kaynakları serbest bırakmak için otomatik olarak çağrılır. Bu, tüm sağlar `CImage` doğrudan veya dolaylı olarak, DLL tarafından oluşturulan nesneler her zaman yok edilir düzgün ve `GdiplusShutdown` gelen çağrılmaz `DllMain`.

> [!NOTE]
> Genel kullanarak `CImage` DLL'de nesneleri önerilmez. Genel bir kullanmanız gerekiyorsa `CImage` DLL'deki, çağrı [CImage::ReleaseGDIPlus](#releasegdiplus) açıkça GDI +'TARAFINDAN kullanılan kaynakları serbest bırakmak için.

`CImage` Yeni bir seçilemez [CDC](../../mfc/reference/cdc-class.md). `CImage` kendi HDC görüntüsü oluşturur. HBITMAP bir HBITMAP yalnızca bir HDC teker teker seçilebilir çünkü ilişkili `CImage` içinde başka bir HDC seçilemez. Bir bu CDC gerekiyorsa, gelen HDC almak `CImage` ve [CDC::FromHandle] için verin (.. /.. /MFC/Reference/cdc-class.MD#cdc__fromhandle.

## <a name="example"></a>Örnek

```cpp
// Get a CDC for the image
CDC* pDC = CDC::FromHandle(m_myImage.GetDC());

// Use pDC here
pDC->Rectangle(0, 40, 100, 50);
m_myImage.ReleaseDC();
```

Kullanırken `CImage` hangi üye işlevleri, projenizdeki bir işaretçiye beklediğiniz bir MFC projesinde Not bir [CBitmap](../../mfc/reference/cbitmap-class.md) nesne. Kullanmak istiyorsanız `CImage` böyle bir işlevi ile gibi [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu), kullanın [CBitmap::FromHandle](../../mfc/reference/cbitmap-class.md#fromhandle), geçirin, `CImage` HBITMAP ve döndürülen `CBitmap*`.

## <a name="example"></a>Örnek

```cpp
void CMyDlg::OnRButtonDown(UINT nFlags, CPoint point)
{
    UNREFERENCED_PARAMETER(nFlags);

    CBitmap* pBitmap = CBitmap::FromHandle(m_myImage);
    m_pmenuPop->AppendMenu(0, ID_BMPCOMMAND, pBitmap);
    ClientToScreen(&point);
    m_pmenuPop->TrackPopupMenu(TPM_RIGHTBUTTON | TPM_LEFTALIGN, point.x,
    point.y, this);
}
```

Aracılığıyla `CImage`, gerçek bit DIB bölümün erişebilirsiniz. Kullanabileceğiniz bir `CImage` daha önce kullandığınız bir Win32 HBITMAP veya DIB bölümü herhangi bir nesne.

Kullanabileceğiniz `CImage` MFC veya ATL

> [!NOTE]
> Kullanarak proje oluşturduğunuzda `CImage`, tanımlamanız gerekir `CString` dahil önce `atlimage.h`. Projenize ATL MFC olmadan kullanıyorsa, dahil `atlstr.h` dahil önce `atlimage.h`. Projeniz MFC (veya bir ATL projesi ile MFC desteği olup olmadığını) kullanıyorsa, dahil `afxstr.h` dahil önce `atlimage.h`.<br/>
> <br/>
> Benzer şekilde, içermelidir `atlimage.h` dahil önce `atlimpl.cpp`. Bunu bir kolayca gerçekleştirmek için dahil `atlimage.h` içinde `stdafx.h`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlimage.h

##  <a name="alphablend"></a>  CImage::AlphaBlend

Saydam veya yarı saydam fırçalarla piksel olan bit eşlemler görüntüler.

```
BOOL AlphaBlend(
    HDC hDestDC,
    int xDest,
    int yDest,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER) const throw();

BOOL AlphaBlend(
    HDC hDestDC,
    const POINT& pointDest,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER) const throw();

BOOL AlphaBlend(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER);

BOOL AlphaBlend(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER);
```

### <a name="parameters"></a>Parametreler

*hDestDC*<br/>
Hedef cihaz bağlamına işleyin.

*xDest*<br/>
X koordinatı, hedef dikdörtgenin sol üst köşesinde, mantıksal birimleri.

*yDest*<br/>
Y koordinatı, hedef dikdörtgenin sol üst köşesinde, mantıksal birimleri.

*bSrcAlpha*<br/>
Tüm kaynak bit eşlem kullanılacak bir saydam alfa değeri. ' % S'varsayılan 0xff (255) görüntünüzü donuk olduğunu ve yalnızca alfa değerleri piksel başına kullanmak istediğinizi varsayar.

*bBlendOp*<br/>
Alfa karıştırma işlev için kaynak ve hedef bit eşlemler, tüm kaynak bit eşlem ve kaynak bit eşlemi için biçim bilgilerini uygulanması için genel bir alfa değeri. Kaynak ve hedef blend işlevleri şu an için AC_SRC_OVER sınırlıdır.

*pointDest*<br/>
Bir başvuru bir [noktası](https://msdn.microsoft.com/library/windows/desktop/dd162805) mantıksal birimler cinsinden hedef dikdörtgenin sol üst köşesinde tanımlayan yapısı.

*nDestWidth*<br/>
Hedef dikdörtgenin mantıksal birimler cinsinden genişliği.

*nDestHeight*<br/>
Hedef dikdörtgenin mantıksal birimler cinsinden yüksekliği.

*Tanımlar*<br/>
Mantıksal x koordinatını kaynak dikdörtgenin sol üst köşesinde.

*ysrc &*<br/>
Mantıksal y koordinatını kaynak dikdörtgenin sol üst köşesinde.

*nSrcWidth*<br/>
Kaynak dikdörtgenin mantıksal birimler cinsinden genişliği.

*nSrcHeight*<br/>
Kaynak dikdörtgenin mantıksal birimler cinsinden yüksekliği.

*rectDest*<br/>
Bir başvuru bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı, hedef belirleme.

*rectSrc*<br/>
Bir başvuru bir `RECT` yapısını tanımlayan kaynak.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Piksel başına temelinde renk karıştırma alfa karıştırma bit eşlemler destekler.

Zaman *bBlendOp* ayarlanır AC_SRC_OVER varsayılana kaynak bit eşlemi hedef bit eşlemi Kaynak piksel alfa değerlerine göre üzerinden yerleştirilir.

##  <a name="attach"></a>  CImage::Attach

Ekler *Hbıtmap* için bir `CImage` nesne.

```
void Attach(HBITMAP hBitmap, DIBOrientation eOrientation = DIBOR_DEFAULT) throw();
```

### <a name="parameters"></a>Parametreler

*Hbıtmap*<br/>
Bir HBITMAP tanıtıcı.

*eOrientation*<br/>
Bit eşlem yönünü belirtir. Aşağıdakilerden biri olabilir:

- Bit eşlem yönünü DIBOR_DEFAULT işletim sistemi tarafından belirlenir.

- Bit eşlem ters sırada satırla DIBOR_BOTTOMUP. Bu neden [CImage::GetBits](#getbits) bit eşlem arabelleğin sonuna yakın bir işaretçiyi döndürmek için ve [CImage::GetPitch](#getpitch) negatif bir sayı dönün.

- Üst alt siparişi için bit eşlem satırlarını bulunan DIBOR_TOPDOWN. Bu neden [CImage::GetBits](#getbits) bit eşlem arabellek ilk baytına bir işaretçi döndürülecek ve [CImage::GetPitch](#getpitch) pozitif bir sayı dönün.

### <a name="remarks"></a>Açıklamalar

Bit eşlem DIB olmayan bölüm bit eşlem ya da bir bit eşlem DIB bölümü olabilir. Bkz: [IsDIBSection](#isdibsection) yalnızca DIB ile kullanabileceğiniz yöntemlerin bir listesi için bit eşlemler bölümü.

##  <a name="bitblt"></a>  CImage::BitBlt

Bir bit eşlemi Kaynak cihaz bağlamında bu geçerli bir cihaz bağlamına kopyalar.

```
BOOL BitBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
    HDC hDestDC,
    const POINT& pointDest,
    DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const POINT& pointSrc,
    DWORD dwROP = SRCCOPY) const throw();
```

### <a name="parameters"></a>Parametreler

*hDestDC*<br/>
Hedef HDC.

*xDest*<br/>
Mantıksal x koordinatını hedef dikdörtgenin sol üst köşesinde.

*yDest*<br/>
Mantıksal y koordinatını hedef dikdörtgenin sol üst köşesinde.

*dwROP*<br/>
Gerçekleştirilecek ızgara işlemi. Izgara işlemi kodları, kaynak, hedef ve desen bit (şu anda seçili fırça tarafından tanımlandığı şekilde) hedef oluşturmak için tam olarak nasıl birleştirileceğini tanımlar. Bkz: [BitBlt](/windows/desktop/api/wingdi/nf-wingdi-bitblt) diğer ızgara işlemi kodları ve açıklamaları listesi için Windows SDK.

*pointDest*<br/>
A [noktası](https://msdn.microsoft.com/library/windows/desktop/dd162805) hedef dikdörtgenin sol üst köşesinde belirten yapısı.

*nDestWidth*<br/>
Hedef dikdörtgenin mantıksal birimler cinsinden genişliği.

*nDestHeight*<br/>
Hedef dikdörtgenin mantıksal birimler cinsinden yüksekliği.

*Tanımlar*<br/>
Mantıksal x koordinatını kaynak dikdörtgenin sol üst köşesinde.

*ysrc &*<br/>
Mantıksal y koordinatını kaynak dikdörtgenin sol üst köşesinde.

*rectDest*<br/>
A [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) hedef dikdörtgenin belirten yapısı.

*pointSrc*<br/>
A `POINT` kaynak dikdörtgenin sol üst köşesinde belirten yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [BitBlt](/windows/desktop/api/wingdi/nf-wingdi-bitblt) Windows SDK.

##  <a name="cimage"></a>  CImage::CImage

Oluşturur bir `CImage` nesne.

```
CImage() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesne oluşturana sonra çağırma [Oluştur](#create), [yük](#load), [LoadFromResource](#loadfromresource), veya [iliştirme](#attach) bir bit eşlem nesnesine eklemek için.

**Not** Visual Studio'da, bu sınıf, bir sayısını tutar `CImage` oluşturulan nesneler. Her sayısı ölçeklendirilinceye 0, işlev `GdiplusShutdown` GDI +'TARAFINDAN kullanılan kaynakları serbest bırakmak için otomatik olarak çağrılır. Bu, tüm sağlar `CImage` doğrudan veya dolaylı olarak, DLL tarafından oluşturulan nesneler her zaman yok edilir düzgün ve `GdiplusShutdown` DllMain'den çağrılmaz.

Genel kullanarak `CImage` DLL'de nesneleri önerilmez. Genel bir kullanmanız gerekiyorsa `CImage` DLL'deki, çağrı [CImage::ReleaseGDIPlus](#releasegdiplus) açıkça GDI +'TARAFINDAN kullanılan kaynakları serbest bırakmak için.

##  <a name="create"></a>  CImage::Create

Oluşturur bir `CImage` bit eşlem ve daha önce oluşturulmuş ekleme `CImage` nesne.

```
BOOL Create(
    int nWidth,
    int nHeight,
    int nBPP,
    DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Parametreler

*nWidth*<br/>
Genişliği `CImage` piksel cinsinden bir bit eşlem.

*nHeight*<br/>
Yüksekliğini `CImage` piksel cinsinden bir bit eşlem. Varsa *nHeight* bit eşlem aşağıdan yukarıya DIB ve kendi başlangıç sol alt köşesine pozitif. Varsa *nHeight* , bit eşlem yukarıdan aşağı DIB negatiftir ve sol üst köşesinde kaynağına ise.

*nBPP*<br/>
Bit eşlemin piksel başına bit sayısı. Genellikle, 4, 8, 16, 24 veya 32. 1 tek renkli bir bit eşlemler veya maskeleri olabilir.

*CertOpenStore*<br/>
Bitmap nesnesi bir alfa kanalı olup olmadığını belirtir. Sıfır veya daha fazla aşağıdaki değerlerin bir birleşimi olabilir:

- *createAlphaChannel* varsa kullanılabilir *nBPP* 32 ' dir ve *eCompression* BI_RGB olduğu. Belirtilmişse, oluşturulmuş görüntü 4 bayt (alfasayısal olmayan 32 bit bir görüntü içinde kullanılmayan) her pikselin depolanan her bir pikseli için bir alfa (Saydamlık) değere sahip. Bu alfa kanalı, otomatik olarak çağrıldığında kullanılır [CImage::AlphaBlend](#alphablend).

> [!NOTE]
> Yapılan çağrıda [CImage::Draw](#draw), alfa kanalı ile görüntüleri otomatik olarak alfa karışık hedef.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

##  <a name="createex"></a>  CImage::CreateEx

Oluşturur bir `CImage` bit eşlem ve daha önce oluşturulmuş ekleme `CImage` nesne.

```
BOOL CreateEx(
    int nWidth,
    int nHeight,
    int nBPP,
    DWORD eCompression,
    const DWORD* pdwBitmasks = NULL,
    DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Parametreler

*nWidth*<br/>
Genişliği `CImage` piksel cinsinden bir bit eşlem.

*nHeight*<br/>
Yüksekliğini `CImage` piksel cinsinden bir bit eşlem. Varsa *nHeight* bit eşlem aşağıdan yukarıya DIB ve kendi başlangıç sol alt köşesine pozitif. Varsa *nHeight* , bit eşlem yukarıdan aşağı DIB negatiftir ve sol üst köşesinde kaynağına ise.

*nBPP*<br/>
Bit eşlemin piksel başına bit sayısı. Genellikle, 4, 8, 16, 24 veya 32. 1 tek renkli bir bit eşlemler veya maskeleri olabilir.

*eCompression*<br/>
Sıkıştırılmış bir aşağıdan yukarıya bit eşlem (yukarıdan aşağıya Dıb'lerin sıkıştırılamaz) için sıkıştırma türünü belirtir. Aşağıdaki değerlerden biri olabilir:

- Sıkıştırılmamış BI_RGB biçimi. Çağrılırken bu değeri belirterek `CImage::CreateEx` çağırmakla eşdeğerdir `CImage::Create`.

- BI_BITFIELDS biçimi sıkıştırılmamış ve renk tablosunu kırmızı, yeşil ve mavi bileşenlerinin sırasıyla her pikseli belirten üç DWORD renk maskeleri oluşur. Bu, bit eşlemler 16 ve 32 bpp kullanıldığında geçerlidir.

*pdwBitfields*<br/>
Yalnızca *eCompression* ayarlanır BI_BITFIELDS için Aksi takdirde, NULL olmalıdır. Hangi bitlerin her pikselin rengin kırmızı, yeşil ve mavi bileşenlerinin sırasıyla kullanılan belirten üç DWORD bit maskesi, bir dizi için bir işaretçi. Bit alanları için kısıtlamaları hakkında daha fazla bilgi için bkz: [BITMAPINFOHEADER](https://msdn.microsoft.com/library/windows/desktop/dd183376) Windows SDK.

*CertOpenStore*<br/>
Bitmap nesnesi bir alfa kanalı olup olmadığını belirtir. Sıfır veya daha fazla aşağıdaki değerlerin bir birleşimi olabilir:

- *createAlphaChannel* varsa kullanılabilir *nBPP* 32 ' dir ve *eCompression* BI_RGB olduğu. Belirtilmişse, oluşturulmuş görüntü 4 bayt (alfasayısal olmayan 32 bit bir görüntü içinde kullanılmayan) her pikselin depolanan her bir pikseli için bir alfa (Saydamlık) değere sahip. Bu alfa kanalı, otomatik olarak çağrıldığında kullanılır [CImage::AlphaBlend](#alphablend).

   > [!NOTE]
   > Yapılan çağrıda [CImage::Draw](#draw), alfa kanalı ile görüntüleri otomatik olarak alfa karışık hedef.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE değeri. Aksi durumda FALSE.

### <a name="example"></a>Örnek

Aşağıdaki örnek, her pikselin kodlamak için 16 bit kullanarak 100 x 100 piksel bit eşlem oluşturur. Belirli bir 16 bit piksel olarak kırmızı bileşeni bitleri 0-3 kodlayın, BITS 4. ve 7 yeşil kodlamak ve BITS 8-11 mavi kodlayın. Kalan 4 kullanılmayan bittir.

```cpp
DWORD adwBitmasks[3] = { 0x0000000f, 0x000000f0, 0x00000f00 };
m_myImage.CreateEx(100, 100, 16, BI_BITFIELDS, adwBitmasks, 0);
```

##  <a name="destroy"></a>  CImage::Destroy

Bit eşlem ayırır `CImage` nesne ve bit eşlem yok eder.

```
void Destroy() throw();
```

##  <a name="detach"></a>  CImage::Detach

Bit eşlemden ayırır bir `CImage` nesne.

```
HBITMAP Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış bit eşlem için bir tanıtıcı veya hiçbir bit eşlem bağlıysa, NULL.

##  <a name="draw"></a>  CImage::Draw

Bir bit eşlemi Kaynak cihaz bağlamında geçerli cihaz bağlamına kopyalar.

```
BOOL Draw(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight) const throw();

BOOL Draw(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc) const throw();

BOOL Draw(
    HDC hDestDC,
    int xDest,
    int yDest) const throw();

BOOL Draw(
    HDC hDestDC,
    const POINT& pointDest) const throw();

BOOL Draw(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight) const throw();

BOOL Draw(
    HDC hDestDC,
    const RECT& rectDest) const throw();
```

### <a name="parameters"></a>Parametreler

*hDestDC*<br/>
Hedef cihaz bağlamının işleyici.

*xDest*<br/>
X koordinatı, hedef dikdörtgenin sol üst köşesinde, mantıksal birimleri.

*yDest*<br/>
Y koordinatı, hedef dikdörtgenin sol üst köşesinde, mantıksal birimleri.

*nDestWidth*<br/>
Hedef dikdörtgenin mantıksal birimler cinsinden genişliği.

*nDestHeight*<br/>
Hedef dikdörtgenin mantıksal birimler cinsinden yüksekliği.

*Tanımlar*<br/>
X koordinatı, kaynak dikdörtgenin sol üst köşesinde, mantıksal birimleri.

*ysrc &*<br/>
Y koordinatı, kaynak dikdörtgenin sol üst köşesinde, mantıksal birimleri.

*nSrcWidth*<br/>
Kaynak dikdörtgenin mantıksal birimler cinsinden genişliği.

*nSrcHeight*<br/>
Kaynak dikdörtgenin mantıksal birimler cinsinden yüksekliği.

*rectDest*<br/>
Bir başvuru bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı, hedef belirleme.

*rectSrc*<br/>
Bir başvuru bir `RECT` yapısını tanımlayan kaynak.

*pointDest*<br/>
Bir başvuru bir [noktası](https://msdn.microsoft.com/library/windows/desktop/dd162805) mantıksal birimler cinsinden hedef dikdörtgenin sol üst köşesinde tanımlayan yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

`Draw` aynı işleme gerçekleştirir [StretchBlt](#stretchblt)resmi saydam rengi ya da alfa kanalını içeren sürece. Bu durumda, `Draw` ya da aynı işleme gerçekleştirir [TransparentBlt](#transparentblt) veya [AlphaBlend](#alphablend) gerektiğinde.

Sürümleri için `Draw` kaynak dikdörtgenin belirlemezseniz, tüm kaynak görüntü varsayılandır. Sürümü için `Draw` hedef dikdörtgenin için bir boyut belirtmiyor, kaynak görüntü boyutu varsayılan ve herhangi bir uzatma veya küçültme gerçekleşir.

##  <a name="getbits"></a>  CImage::GetBits

Bir bit eşlem içindeki belirli bir pikselin gerçek bit değerleri için bir işaretçi alır.

```
void* GetBits() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bit eşlem arabellek için işaretçi. Ukazatel ukazuje, bit eşlem aşağıdan yukarıya DIB ise, arabelleğin sonuna yakın. Bit eşlem yukarıdan aşağı DIB ise, işaretçinin arabellek ilk baytı için işaret eder.

### <a name="remarks"></a>Açıklamalar

Tarafından döndürülen değerin yanı sıra bu işaretçisi kullanılarak [GetPitch](#getpitch), bulun ve görüntünün tek tek her piksel ile değiştirin.

> [!NOTE]
> Bu yöntem yalnızca DIB bölüm bit eşlemler destekler. Sonuç olarak, size piksel erişim bir `CImage` DIB bölümün piksel olduğu gibi nesne. Döndürülen işaretçi (0, 0) konumundaki piksel işaret eder.

##  <a name="getbpp"></a>  CImage::GetBPP

Piksel başına bit değeri alır.

```
int GetBPP() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Piksel başına bit sayısı.

### <a name="remarks"></a>Açıklamalar

Bu değer, her pikselin tanımlayan bit sayısını ve renk bit eşlemde maksimum sayısını belirler.

Piksel başına bit olduğundan genellikle 1, 4, 8, 16, 24 veya 32. Bkz: `biBitCount` üyesi [BITMAPINFOHEADER](https://msdn.microsoft.com/library/windows/desktop/dd183376) bu değeri hakkında daha fazla bilgi için Windows SDK.

##  <a name="getcolortable"></a>  CImage::GetColorTable

Kırmızı, yeşil, mavi (RGB) renk değerleri DIB bölümünün paleti girdileri aralığını alır.

```
void GetColorTable(
    UINT iFirstColor,
    UINT nColors,
    RGBQUAD* prgbColors) const throw();
```

### <a name="parameters"></a>Parametreler

*iFirstColor*<br/>
Alınacak ilk giriş renk tablosu dizini.

*nColors*<br/>
Alınacak renkli Tablo girdileri sayısı.

*prgbColors*<br/>
Bir işaretçi dizisinin işaretçisi [RGBQUAD](/windows/desktop/api/wingdi/ns-wingdi-tagrgbquad) rengini almak için yapılar tablo girişleri.

##  <a name="getdc"></a>  CImage::GetDC

Şu anda görüntü içine seçili olan cihaz bağlamı alır.

```
HDC GetDC() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir cihaz bağlamı için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Her çağrı için `GetDC`, bir sonraki çağrı olmalıdır [ReleaseDC](#releasedc).

##  <a name="getexporterfilterstring"></a>  CImage::GetExporterFilterString

Görüntüleri kaydetmek için kullanılabilir görüntü biçimlerini bulur.

```
static HRESULT GetExporterFilterString(
    CSimpleString& strExporters,
    CSimpleArray<GUID>& aguidFileTypes,
    LPCTSTR pszAllFilesDescription = NULL,
    DWORD dwExclude = excludeDefaultSave,
    TCHAR chSeparator = _T('|'));
```

### <a name="parameters"></a>Parametreler

*strExporters*<br/>
Bir başvuru bir `CSimpleString` nesne. Bkz: **açıklamalar** daha fazla bilgi için.

*aguidFileTypes*<br/>
GUID'ler, dizedeki dosya türlerinden birini karşılık gelen her öğe dizisi. Örnekte *pszAllFilesDescription* aşağıdaki *aguidFileTypes*[0] GUID_NULL ve kalan dizi değerlerini geçerli işletim sistemi tarafından desteklenen görüntü dosyası biçimlerini.

> [!NOTE]
> Sabitler tam bir listesi için bkz. **görüntü dosya biçimi sabitleri** Windows SDK.

*pszAllFilesDescription*<br/>
Bu parametre NULL değilse, filtre dizesi listenin başında bir ek filtre gerekir. Bu filtre, geçerli değerini olacaktır *pszAllFilesDescription* açıklaması için listedeki diğer dışarı Aktarıcı tarafından desteklenen herhangi bir genişletme dosya kabul eder.

Örneğin:

```cpp
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any exporter.
CImage::GetExporterFilterString(
    strExporters, aguidFileTypes,
_T("All Image Files"));
```

*dwExclude*<br/>
Bit bayrakları listesinden Dışlanmak için hangi dosya türlerinin belirten dizi. İzin verilen bayraklar:

- `excludeGIF` 0x01 dışlar GIF dosyaları =.

- `excludeBMP` 0x02 dışlar BMP (Windows bit eşlem) dosyaları =.

- `excludeEMF` 0x04 dışlar EMF (Gelişmiş Meta dosyası) dosyaları =.

- `excludeWMF` 0x08 dışlar WMF (Windows Meta dosyası) dosyaları =.

- `excludeJPEG` 0x10 dışlar JPEG dosyaları =.

- `excludePNG` 0x20 dışlar PNG dosyaları =.

- `excludeTIFF` 0x40 dışlar TIFF dosyaları =.

- `excludeIcon` 0x80 dışlar ICO (Windows simge) dosyaları =.

- `excludeOther` = 0x80000000 Yukarıda listelenmeyen başka bir dosya türü dışlar.

- `excludeDefaultLoad` Yük, tüm dosya türleri varsayılan olarak dahil 0 =

- `excludeDefaultSave` = `excludeIcon &#124; excludeEMF &#124; excludeWMF` Genellikle özel gereksinimler sahip oldukları için kaydetme, varsayılan olarak bu dosyaları hariç tutulur.

*chSeparator*<br/>
Resim biçimleri arasında kullanılan ayırıcı. Bkz: **açıklamalar** daha fazla bilgi için.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Sonuç biçimi dizesi, MFC'ye geçirebilirsiniz [CFileDialog](../../mfc/reference/cfiledialog-class.md) kullanılabilir görüntüsünün dosya uzantılarını kullanıma sunmak için nesne dosyayı farklı Kaydet iletişim kutusunda biçimlendirir.

Parametre *strExporter* şu biçimdedir:

description0 dosya&#124;\*.ext0&#124;filedescription1&#124;\*.ext1&#124;.. .file açıklama *n*&#124;\*.Ext .ext *n*&#124;&#124;

Burada '&#124;' ayırıcı karakteri tarafından belirtilen `chSeparator`. Örneğin:

`"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`

Varsayılan ayırıcı kullan '&#124;' için bir MFC bu dize geçirirseniz `CFileDialog` nesne. Ortak Dosya Kaydet iletişim kutusu için bu dize geçirirseniz, null ayırıcı '\0' kullanın.

##  <a name="getheight"></a>  CImage::GetHeight

Piksel cinsinden görüntü yüksekliği alır.

```
int GetHeight() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Piksel cinsinden görüntü yüksekliği.

##  <a name="getimporterfilterstring"></a>  CImage::GetImporterFilterString

Görüntü yüklemek için kullanılabilir görüntü biçimlerini bulur.

```
static HRESULT GetImporterFilterString(
    CSimpleString& strImporters,
    CSimpleArray<GUID>& aguidFileTypes,
    LPCTSTR pszAllFilesDescription = NULL,
    DWORD dwExclude = excludeDefaultLoad,
    TCHAR chSeparator = _T('|'));
```

### <a name="parameters"></a>Parametreler

*strImporters*<br/>
Bir başvuru bir `CSimpleString` nesne. Bkz: **açıklamalar** daha fazla bilgi için.

*aguidFileTypes*<br/>
GUID'ler, dizedeki dosya türlerinden birini karşılık gelen her öğe dizisi. Örnekte *pszAllFilesDescription* aşağıdaki *aguidFileTypes*[0] GUID_NULL kalan dizi değerlerini ile geçerli işletim sistemi tarafından desteklenen görüntü dosyası biçimlerini vardır.

> [!NOTE]
> Sabitler tam bir listesi için bkz. **görüntü dosya biçimi sabitleri** Windows SDK.

*pszAllFilesDescription*<br/>
Bu parametre NULL değilse, filtre dizesi listenin başında bir ek filtre gerekir. Bu filtre, geçerli değerini olacaktır *pszAllFilesDescription* açıklaması için listedeki diğer dışarı Aktarıcı tarafından desteklenen herhangi bir genişletme dosya kabul eder.

Örneğin:

```cpp
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any importer.
CImage::GetImporterFilterString(
    strImporters, aguidFileTypes,
_T("All Image Files"));
```

*dwExclude*<br/>
Bit bayrakları listesinden Dışlanmak için hangi dosya türlerinin belirten dizi. İzin verilen bayraklar:

- `excludeGIF` 0x01 dışlar GIF dosyaları =.

- `excludeBMP` 0x02 dışlar BMP (Windows bit eşlem) dosyaları =.

- `excludeEMF` 0x04 dışlar EMF (Gelişmiş Meta dosyası) dosyaları =.

- `excludeWMF` 0x08 dışlar WMF (Windows Meta dosyası) dosyaları =.

- `excludeJPEG` 0x10 dışlar JPEG dosyaları =.

- `excludePNG` 0x20 dışlar PNG dosyaları =.

- `excludeTIFF` 0x40 dışlar TIFF dosyaları =.

- `excludeIcon` 0x80 dışlar ICO (Windows simge) dosyaları =.

- `excludeOther` = 0x80000000 Yukarıda listelenmeyen başka bir dosya türü dışlar.

- `excludeDefaultLoad` Yük, tüm dosya türleri varsayılan olarak dahil 0 =

- `excludeDefaultSave` = `excludeIcon &#124; excludeEMF &#124; excludeWMF` Genellikle özel gereksinimler sahip oldukları için kaydetme, varsayılan olarak bu dosyaları hariç tutulur.

*chSeparator*<br/>
Resim biçimleri arasında kullanılan ayırıcı. Bkz: **açıklamalar** daha fazla bilgi için.

### <a name="remarks"></a>Açıklamalar

Sonuç biçimi dizesi, MFC'ye geçirebilirsiniz [CFileDialog](../../mfc/reference/cfiledialog-class.md) kullanılabilir görüntüsünün dosya uzantılarını kullanıma sunmak için nesneyi biçimlendirir **Dosya Aç** iletişim kutusu.

Parametre *strImporter* şu biçimdedir:

description0 dosya&#124;\*.ext0&#124;filedescription1&#124;\*.ext1&#124;.. .file açıklama *n*&#124;\*.Ext .ext *n*&#124;&#124;

Burada '&#124;' tarafından belirtilen bir ayırıcı karakter *chSeparator*. Örneğin:

`"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`

Varsayılan ayırıcı kullan '&#124;' için bir MFC bu dize geçirirseniz `CFileDialog` nesne. Bu dize bir ortak geçirirseniz, null ayırıcı '\0' kullanmak **Dosya Aç** iletişim kutusu.

##  <a name="getmaxcolortableentries"></a>  CImage::GetMaxColorTableEntries

Renkli Tablo girdileri maksimum sayısını alır.

```
int GetMaxColorTableEntries() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Renkli Tablo girdileri sayısı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca DIB bölüm bit eşlemler destekler.

##  <a name="getpitch"></a>  CImage::GetPitch

Görüntü aralığını alır.

```
int GetPitch() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Görüntünün aralığı. Dönüş değeri negatifse, bit eşlem aşağıdan yukarıya DIB ve kendi başlangıç sol alt köşesine. Dönüş değeri bir bit eşlem yukarıdan aşağı DIB ve kendi başlangıç sol üst köşesinde pozitif ise.

### <a name="remarks"></a>Açıklamalar

Aralık bayt cinsinden temsil eden bir bit eşlem satırın başına iki bellek adresi ve sonraki bit eşlem satır başlangıcı arasındaki uzaklığı ' dir. Aralık bayt cinsinden ölçülen olduğundan, görüntünün aralığı piksel biçimini belirlemek için yardımcı olur. Aralık için bit eşlem ayrılmış ek bellek de içerebilir.

Kullanım `GetPitch` ile [GetBits](#getbits) tek tek her piksel görüntü bulunamadı.

> [!NOTE]
> Bu yöntem yalnızca DIB bölüm bit eşlemler destekler.

##  <a name="getpixel"></a>  CImage::GetPixel

Tarafından belirtilen konumda piksel rengi alır *x* ve *y*.

```
COLORREF GetPixel(int x, int y) const throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
X koordinatı piksel.

*Y*<br/>
Y koordinatını piksel.

### <a name="return-value"></a>Dönüş Değeri

Kırmızı, yeşil, mavi (RGB) değeri piksel. Piksel geçerli kırpma bölgesinin dışında ise, dönüş değeri clr_ınvalıd ' dir.

##  <a name="getpixeladdress"></a>  CImage::GetPixelAddress

Bir pikselin tam adresi alır.

```
void* GetPixelAddress(int x, int y) throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
X koordinatı piksel.

*Y*<br/>
Y koordinatını piksel.

### <a name="remarks"></a>Açıklamalar

Adres koordinatlarını bir piksel, bit eşlem ve piksel başına bit aralığını göre belirlenir.

Bu yöntem, sahip değerinden 8 bit / piksel biçimleri için piksel içeren bayt adresini döndürür. Örneğin, görüntü biçimi 4 bit / piksel, varsa, `GetPixelAddress` gerekir bayt ve ilk piksel adresini döndürür hesaplamak için bayt başına 2 piksel.

> [!NOTE]
> Bu yöntem yalnızca DIB bölüm bit eşlemler destekler.

##  <a name="gettransparentcolor"></a>  CImage::GetTransparentColor

Renk paletini saydam rengi dizinli konumunu alır.

```
LONG GetTransparentColor() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Saydam Rengi dizini.

##  <a name="getwidth"></a>  CImage::GetWidth

Piksellerde görüntü genişliğini alır.

```
int GetWidth() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bit eşlemin piksel cinsinden genişliği.

##  <a name="isdibsection"></a>  CImage::IsDIBSection

Ekli bit eşlem DIB bölümü olup olmadığını belirler.

```
bool IsDIBSection() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ekli bit eşlem DIB bölüm ise TRUE. Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bit eşlem DIB bölüm değilse, aşağıdaki kullanamazsınız `CImage` yalnızca DIB bölüm bit eşlemler destekleyen yöntemler:

- [GetBits](#getbits)

- [GetColorTable](#getcolortable)

- [GetMaxColorTableEntries](#getmaxcolortableentries)

- [GetPitch](#getpitch)

- [GetPixelAddress](#getpixeladdress)

- [IsIndexed](#isindexed)

- [SetColorTable](#setcolortable)

##  <a name="isindexed"></a>  CImage::IsIndexed

Bir bit eşleşmemin piksel renk paleti için eşlenen olup olmadığını belirler.

```
bool IsIndexed() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dizine TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Yalnızca 8-bit bit eşlem olduğunda bu yöntem, TRUE döndürür. (256 renk) veya daha az.

> [!NOTE]
> Bu yöntem yalnızca DIB bölüm bit eşlemler destekler.

##  <a name="isnull"></a>  CImage::IsNull

Bir bit eşlem şu anda yüklü olan belirler.

```
bool IsNull() const throw();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir bit eşlem şu anda yüklü değilse, TRUE döndürür; Aksi durumda FALSE.

##  <a name="istransparencysupported"></a>  CImage::IsTransparencySupported

Uygulama saydam bit eşlemler destekleyip desteklemediğini belirtir.

```
static BOOL IsTransparencySupported() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli platform saydamlık destekliyorsa, sıfır dışında. Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri sıfır ise ve saydamlık desteklenir, çağrı [AlphaBlend](#alphablend), [TransparentBlt](#transparentblt), veya [çizmek](#draw) saydam renkleri işler.

##  <a name="load"></a>  CImage::Load

Görüntüyü yükler.

```
HRESULT Load(LPCTSTR pszFileName) throw();
HRESULT Load(IStream* pStream) throw();
```

### <a name="parameters"></a>Parametreler

*pszFileName*<br/>
Yüklemek için resim dosyası adını içeren bir dize işaretçisi.

*pStream*<br/>
Yüklemek için resim dosyası adını içeren bir akış için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Tarafından belirtilen görüntü yükleyen *pszFileName* veya *pStream*.

Geçerli görüntü BMP, GIF, JPEG, PNG ve TIFF türleridir.

##  <a name="loadfromresource"></a>  CImage::LoadFromResource

Görüntü bit eşlem kaynağı yükler.

```
void LoadFromResource(
    HINSTANCE hInstance,
    LPCTSTR pszResourceName) throw();

void LoadFromResource(
    HINSTANCE hInstance,
    UINT nIDResource) throw();
```

### <a name="parameters"></a>Parametreler

*HINSTANCE*<br/>
Yüklenen görüntüyü içeren modül örneğine işleyin.

*pszResourceName*<br/>
Yüklemek için görüntüyü içeren kaynak adını içeren dize işaretçisi.

*nIDResource*<br/>
Yüklemek için kaynak kimliği.

### <a name="remarks"></a>Açıklamalar

Kaynak bit eşlem türünde olmalıdır.

##  <a name="maskblt"></a>  CImage::MaskBlt

Belirtilen maske ve ızgara işlemi kullanarak kaynak ve hedef bit eşlemler için renk verileri birleştirir.

```
BOOL MaskBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    HBITMAP hbmMask,
    int xMask,
    int yMask,
    DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const POINT& pointSrc,
    HBITMAP hbmMask,
    const POINT& pointMask,
    DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    HBITMAP hbmMask,
    DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
    HDC hDestDC,
    const POINT& pointDest,
    HBITMAP hbmMask,
    DWORD dwROP = SRCCOPY) const throw();
```

### <a name="parameters"></a>Parametreler

*hDestDC*<br/>
Kaynak olan yürütülebilir dosya içeren modül tanıtıcısını.

*xDest*<br/>
X koordinatı, hedef dikdörtgenin sol üst köşesinde, mantıksal birimleri.

*yDest*<br/>
Y koordinatı, hedef dikdörtgenin sol üst köşesinde, mantıksal birimleri.

*nDestWidth*<br/>
Hedef dikdörtgenin ve kaynak bit eşlemi, mantıksal birimler cinsinden genişliği.

*nDestHeight*<br/>
Hedef dikdörtgenin ve kaynak bit eşlemi, mantıksal birimler cinsinden yüksekliği.

*Tanımlar*<br/>
Mantıksal x koordinatını kaynak bit eşlemi sol üst köşesinde.

*ysrc &*<br/>
Mantıksal y koordinatını kaynak bit eşlemi sol üst köşesinde.

*hbmMask*<br/>
Renk bit eşlemi Kaynak cihaz bağlamındaki birlikte, bit eşlemi renkliye dönüştürmesi gerekirse maskesi işleyin.

*xMask*<br/>
Tarafından belirtilen maskesi eşlemiyle yatay piksel uzaklığı *hbmMask* parametresi.

*yMask*<br/>
Tarafından belirtilen maskesi eşlemiyle dikey piksel uzaklığı *hbmMask* parametresi.

*dwROP*<br/>
Ön ve arka plan Üçlü ızgara işlemi birleşimi, kaynak ve hedef veri denetlemek için yöntemini kullanan kodları belirtir. Arka plan tarama işlem kodu dwpoint bu değerinin yüksek düzeyli baytı depolanır; ön plan tarama işlem kodu dwpoint bu değerinin düşük baytını depolanır; Bu değer, düşük düzey word göz ardı edilir ve sıfır olmalıdır. Ön plan ve arka plan bağlamında, bu yöntem bir tartışma için bkz `MaskBlt` Windows SDK. Ortak ızgara işlemi kodları listesi için bkz. `BitBlt` Windows SDK.

*rectDest*<br/>
Bir başvuru bir `RECT` yapısı, hedef belirleme.

*pointSrc*<br/>
A `POINT` kaynak dikdörtgenin sol üst köşesinde belirten yapısı.

*pointMask*<br/>
A `POINT` maskesi bit eşlem sol üst köşesinde belirten yapısı.

*pointDest*<br/>
Bir başvuru bir `POINT` mantıksal birimler cinsinden hedef dikdörtgenin sol üst köşesinde tanımlayan yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem Windows NT 4.0 ve üzeri sürümler için geçerlidir.

##  <a name="operator_hbitmap"></a>  HBITMAP CImage::operator

Ekli Windows GDI tanıtıcısını almak için bu işleci kullanın `CImage` nesne. HBITMAP nesne doğrudan kullanımını destekleyen bir yayım işleciyle işlecidir.

##  <a name="plgblt"></a>  CImage::PlgBlt

Bit bloğu aktarımı bir hedef cihaz bağlamında bir eğdiğinizde Paralel Kenar içine bir dikdörtgenden kaynak cihaz bağlamında gerçekleştirir.

```
BOOL PlgBlt(
    HDC hDestDC,
    const POINT* pPoints,
    HBITMAP hbmMask = NULL) const throw();

BOOL PlgBlt(
    HDC hDestDC,
    const POINT* pPoints,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    HBITMAP hbmMask = NULL,
    int xMask = 0,
    int yMask = 0) const throw();

BOOL PlgBlt(
    HDC hDestDC,
    const POINT* pPoints,
    const RECT& rectSrc,
    HBITMAP hbmMask = NULL,
    const POINT& pointMask = CPoint(0, 0)) const throw();
```

### <a name="parameters"></a>Parametreler

*hDestDC*<br/>
Hedef cihaz bağlamının işleyici.

*pPoints*<br/>
Hedef eğdiğinizde Paralel Kenar üç köşelerini tanımlayan üç nokta mantıksal alan içinde bir dizi için bir işaretçi. Kaynak dikdörtgenin sol üst köşesinde bu dizi, bu dizinin ikinci noktasına sağ üst köşenin ve sol alt köşesine üçüncü noktasına ilk noktanın eşleştirilir. Kaynak dikdörtgenin sağ alt köşedeki eğdiğinizde Paralel Kenar dördüncü örtülü noktasına eşlenir.

*hbmMask*<br/>
Kaynak dikdörtgenin renkleri maskelemek için kullanılan isteğe bağlı tek renkli bir bitmap işleyici.

*Tanımlar*<br/>
X koordinatı, kaynak dikdörtgenin sol üst köşesinde, mantıksal birimleri.

*ysrc &*<br/>
Y koordinatı, kaynak dikdörtgenin sol üst köşesinde, mantıksal birimleri.

*nSrcWidth*<br/>
Kaynak dikdörtgenin mantıksal birimler cinsinden genişliği.

*nSrcHeight*<br/>
Kaynak dikdörtgenin mantıksal birimler cinsinden yüksekliği.

*xMask*<br/>
Bit eşlemi renkliye dönüştürmesi gerekirse sol üst köşesinin x-koordinatı.

*yMask*<br/>
Bit eşlemi renkliye dönüştürmesi gerekirse sol üst köşesinin y-koordinatı.

*rectSrc*<br/>
Bir başvuru bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı koordinatları kaynak dikdörtgenin belirtme.

*pointMask*<br/>
A [noktası](https://msdn.microsoft.com/library/windows/desktop/dd162805) maskesi bit eşlem sol üst köşesinde belirten yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsa *hbmMask* geçerli tek renkli bir bitmap tanımlayan `PlgBit` bu bit eşlemi Kaynak dikdörtgenden renk verileri bit maskesi için kullanır.

Bu yöntem Windows NT 4.0 ve üzeri sürümler için geçerlidir. Bkz: [PlgBlt](/windows/desktop/api/wingdi/nf-wingdi-plgblt) daha ayrıntılı bilgi için Windows SDK.

##  <a name="releasedc"></a>  CImage::ReleaseDC

Cihaz bağlamı serbest bırakır.

```
void ReleaseDC() const throw();
```

### <a name="remarks"></a>Açıklamalar

Bir cihaz bağlamına aynı anda yalnızca bir bit eşlem seçilebilir çünkü çağırmalısınız `ReleaseDC` her çağrı için [GetDC](#getdc).

##  <a name="releasegdiplus"></a>  CImage::ReleaseGDIPlus

GDI +'TARAFINDAN kullanılan kaynakları serbest bırakır.

```
void ReleaseGDIPlus() throw();
```

### <a name="remarks"></a>Açıklamalar

Genel ayrılan kaynakları serbest bırakmak için bu yöntem çağrılmalıdır `CImage` nesne. Bkz: [CImage::CImage](#cimage).

##  <a name="save"></a>  CImage::Save

Görüntüyü belirtilen akış veya dosya diskte kaydeder.

```
HRESULT Save(
    IStream* pStream,
    REFGUID guidFileType) const throw();

HRESULT Save(
    LPCTSTR pszFileName,
    REFGUID guidFileType = GUID_NULL) const throw();
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
Dosya resim verilerini içeren bir COM IStream nesnesine bir işaretçi.

*pszFileName*<br/>
Görüntü için dosya adı için bir işaretçi.

*guidFileType*<br/>
Resmi olarak kaydetmek için dosya türü. Aşağıdakilerden biri olabilir:

- `ImageFormatBMP` Sıkıştırılmamış bit eşlem görüntüsü.

- `ImageFormatPNG` Taşınabilir Ağ Grafik (PNG) bir sıkıştırılmış görüntü.

- `ImageFormatJPEG` Bir JPEG görüntüsünü sıkıştırılmış.

- `ImageFormatGIF` Bir GIF görüntüsünü sıkıştırılmış.

> [!NOTE]
> Sabitler tam bir listesi için bkz. **görüntü dosya biçimi sabitleri** Windows SDK.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Belirtilen adı ve türü kullanılarak görüntüsünü kaydetmek için bu işlevi çağırın. Varsa *guidFileType* parametresi dahil değil, dosya adı dosya uzantısı görüntü biçimi belirlemek için kullanılır. Hiçbir uzantı sağlanırsa, görüntünün BMP biçiminde kaydedilir.

##  <a name="setcolortable"></a>  CImage::SetColorTable

Kırmızı, yeşil, mavi (RGB) renk değerleri bir dizi giriş palette DIB bölümünün ayarlar.

```
void SetColorTable(
    UINT iFirstColor,
    UINT nColors,
    const RGBQUAD* prgbColors) throw();
```

### <a name="parameters"></a>Parametreler

*iFirstColor*<br/>
İlk giriş ayarlamak için renk tablosu dizini.

*nColors*<br/>
Ayarlanacak renkli Tablo girdileri sayısı.

*prgbColors*<br/>
Bir işaretçi dizisinin işaretçisi [RGBQUAD](/windows/desktop/api/wingdi/ns-wingdi-tagrgbquad) girişlerini yapıları rengini ayarlamak için tablo.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca DIB bölüm bit eşlemler destekler.

##  <a name="setpixel"></a>  CImage::SetPixel

Bit eşlem belirli bir konumda bir piksel rengini ayarlar.

```
void SetPixel(int x, int y, COLORREF color) throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Ayarlanacak piksel yatay konumu.

*Y*<br/>
Ayarlanacak piksel dikey konumu.

*Renk*<br/>
Piksel ayarladığınız rengi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem kalan seçili kırpma bölgesinin dışındaki piksel koordinatları başarısız olur.

##  <a name="setpixelindexed"></a>  CImage::SetPixelIndexed

Piksel rengi konumundaki rengine ayarlar *İIndex* renk paletindeki.

```
void SetPixelIndexed(int x, int y, int iIndex) throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Ayarlanacak piksel yatay konumu.

*Y*<br/>
Ayarlanacak piksel dikey konumu.

*İIndex*<br/>
Renk paletini renkte dizini.

##  <a name="setpixelrgb"></a>  CImage::SetPixelRGB

Tarafından belirtilen konumlarda piksel ayarlar *x* ve *y* belirttiği renklere *r*, *g*, ve *b*, bir kırmızı, yeşil, mavi (RGB) görüntüsü.

```
void SetPixelRGB(
    int x,
    int y,
    BYTE r,
    BYTE g,
    BYTE b) throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Ayarlanacak piksel yatay konumu.

*Y*<br/>
Ayarlanacak piksel dikey konumu.

*r*<br/>
Kırmızı renkli yoğunluğu.

*g*<br/>
Yeşil renk yoğunluğu.

*b*<br/>
Mavi renk yoğunluğu.

### <a name="remarks"></a>Açıklamalar

Kırmızı, yeşil ve mavi parametreleri her 0 ile 255 arasında bir sayı olarak temsil edilir. Tüm üç parametre sıfır olarak ayarlayın, birleşik ortaya çıkan rengi siyah olur. Tüm üç parametre 255'e ayarlayın, birleşik ortaya çıkan rengi beyaz olur.

##  <a name="settransparentcolor"></a>  CImage::SetTransparentColor

Saydam olarak verilen dizinli konumdaki bir rengini ayarlar.

```
LONG SetTransparentColor(LONG iTransparentColor) throw();
```

### <a name="parameters"></a>Parametreler

*iTransparentColor*<br/>
Bir renk paletini, ayarlamak için saydam için renk dizini. -1, renk saydam olarak ayarlıdır.

### <a name="return-value"></a>Dönüş Değeri

Renk dizini, daha önce saydam olarak ayarlayın.

##  <a name="stretchblt"></a>  CImage::StretchBlt

Bir bit eşlemi Kaynak cihaz bağlamında bu geçerli bir cihaz bağlamına kopyalar.

```
BOOL StretchBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
    HDC hDestDC,
    const RECT& rectDest,
    DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc,
    DWORD dwROP = SRCCOPY) const throw();
```

### <a name="parameters"></a>Parametreler

*hDestDC*<br/>
Hedef cihaz bağlamının işleyici.

*xDest*<br/>
X koordinatı, hedef dikdörtgenin sol üst köşesinde, mantıksal birimleri.

*yDest*<br/>
Y koordinatı, hedef dikdörtgenin sol üst köşesinde, mantıksal birimleri.

*nDestWidth*<br/>
Hedef dikdörtgenin mantıksal birimler cinsinden genişliği.

*nDestHeight*<br/>
Hedef dikdörtgenin mantıksal birimler cinsinden yüksekliği.

*dwROP*<br/>
Gerçekleştirilecek ızgara işlemi. Izgara işlemi kodları, kaynak, hedef ve desen bit (şu anda seçili fırça tarafından tanımlandığı şekilde) hedef oluşturmak için tam olarak nasıl birleştirileceğini tanımlar. Bkz: [BitBlt](/windows/desktop/api/wingdi/nf-wingdi-bitblt) diğer ızgara işlemi kodları ve açıklamaları listesi için Windows SDK.

*rectDest*<br/>
Bir başvuru bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı, hedef belirleme.

*Tanımlar*<br/>
X koordinatı, kaynak dikdörtgenin sol üst köşesinde, mantıksal birimleri.

*ysrc &*<br/>
Y koordinatı, kaynak dikdörtgenin sol üst köşesinde, mantıksal birimleri.

*nSrcWidth*<br/>
Kaynak dikdörtgenin mantıksal birimler cinsinden genişliği.

*nSrcHeight*<br/>
Kaynak dikdörtgenin mantıksal birimler cinsinden yüksekliği.

*rectSrc*<br/>
Bir başvuru bir `RECT` yapısını tanımlayan kaynak.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [StretchBlt](/windows/desktop/api/wingdi/nf-wingdi-stretchblt) Windows SDK.

##  <a name="transparentblt"></a>  CImage::TransparentBlt

Bir bit eşlemi Kaynak cihaz bağlamında bu geçerli bir cihaz bağlamına kopyalar.

```
BOOL TransparentBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
    HDC hDestDC,
    const RECT& rectDest,
    UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc,
    UINT crTransparent = CLR_INVALID) const throw();
```

### <a name="parameters"></a>Parametreler

*hDestDC*<br/>
Hedef cihaz bağlamının işleyici.

*xDest*<br/>
X koordinatı, hedef dikdörtgenin sol üst köşesinde, mantıksal birimleri.

*yDest*<br/>
Y koordinatı, hedef dikdörtgenin sol üst köşesinde, mantıksal birimleri.

*nDestWidth*<br/>
Hedef dikdörtgenin mantıksal birimler cinsinden genişliği.

*nDestHeight*<br/>
Hedef dikdörtgenin mantıksal birimler cinsinden yüksekliği.

*crTransparent*<br/>
Saydam olarak değerlendirilecek kaynak bit eşlemi rengi. Varsayılan olarak, clr_ınvalıd, renk resminin saydam rengi ayarlanmış olduğunu belirten kullanılmalıdır.

*rectDest*<br/>
Bir başvuru bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı, hedef belirleme.

*Tanımlar*<br/>
X koordinatı, kaynak dikdörtgenin sol üst köşesinde, mantıksal birimleri.

*ysrc &*<br/>
Y koordinatı, kaynak dikdörtgenin sol üst köşesinde, mantıksal birimleri.

*nSrcWidth*<br/>
Kaynak dikdörtgenin mantıksal birimler cinsinden genişliği.

*nSrcHeight*<br/>
Kaynak dikdörtgenin mantıksal birimler cinsinden yüksekliği.

*rectSrc*<br/>
Bir başvuru bir `RECT` yapısını tanımlayan kaynak.

### <a name="return-value"></a>Dönüş Değeri

Başarılı, aksi takdirde FALSE ise TRUE.

### <a name="remarks"></a>Açıklamalar

`TransparentBlt` Kaynak bit eşlemleri 4 bit / piksel ve 8 bit / piksel desteklenir. Kullanım [CImage::AlphaBlend](#alphablend) saydamlığı olan 32 bit-piksel başına bit eşlemler belirtmek için.

### <a name="example"></a>Örnek

```cpp
// Performs a transparent blit from the source image to the destination
// image using the images' current transparency settings
BOOL TransparentBlt(CImage* pSrcImage, CImage* pDstImage,
       int xDest, int yDest, int nDestWidth, int nDestHeight)
{
    HDC hDstDC = NULL;
    BOOL bResult;

    if(pSrcImage == NULL || pDstImage == NULL)
    {
        // Invalid parameter
        return FALSE;
    }

    // Obtain a DC to the destination image
    hDstDC = pDstImage->GetDC();
    // Perform the blit
    bResult = pSrcImage->TransparentBlt(hDstDC, xDest, yDest, nDestWidth, nDestHeight);

    // Release the destination DC
    pDstImage->ReleaseDC();

    return bResult;
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[MMXSwarm örnek](../../visual-cpp-samples.md)<br/>
[SimpleImage örnek](../../visual-cpp-samples.md)<br/>
[CİHAZDAN bağımsız bit eşlemler](/windows/desktop/gdi/device-independent-bitmaps)<br/>
[CreateDIBSection](/windows/desktop/api/wingdi/nf-wingdi-createdibsection)<br/>
[ATL COM Masaüstü Bileşenleri](../../atl/atl-com-desktop-components.md)<br/>
[CİHAZDAN bağımsız bit eşlemler](/windows/desktop/gdi/device-independent-bitmaps)<br/>
[CreateDIBSection](/windows/desktop/api/wingdi/nf-wingdi-createdibsection)
