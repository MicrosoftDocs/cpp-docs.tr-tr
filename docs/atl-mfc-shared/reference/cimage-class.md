---
title: CImage Sınıfı
ms.date: 08/19/2019
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
ms.openlocfilehash: 5b5ef833a3755b07e42a60b24464b1f260062d16
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317820"
---
# <a name="cimage-class"></a>CImage Sınıfı

`CImage`JPEG, GIF, BMP ve Taşınabilir Ağ Grafikleri (PNG) biçimlerinde görüntü yükleme ve kaydetme olanağı da dahil olmak üzere gelişmiş bit map desteği sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CImage
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CImage::CImage](#cimage)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CImage::AlphaBlend](#alphablend)|Saydam veya yarı saydam piksellere sahip bit eşlemleri görüntüler.|
|[CImage::Ekle](#attach)|Bir nesneye HBITMAP `CImage` ataşıyor. DIB olmayan bölüm bit eşlemleri veya DIB kesit bit eşlemleri ile kullanılabilir.|
|[CImage::BitBlt](#bitblt)|Kaynak aygıt bağlamından bu geçerli aygıt bağlamına bir bit eşlemi kopyalar.|
|[CImage::Oluştur](#create)|DIB bölüm bit eşlemi oluşturur ve daha `CImage` önce oluşturulmuş nesneye bağlar.|
|[CImage::CreateEx](#createex)|DiB bölüm bit eşlemi (ek parametrelerle) oluşturur ve `CImage` daha önce oluşturulmuş nesneye bağlar.|
|[CImage::Destroy](#destroy)|Bit eşlemi `CImage` nesneden ayırır ve bit eşlemi yok eder.|
|[CImage::Detach](#detach)|Bit eşlemi bir `CImage` nesneden ayırır.|
|[CImage::Draw](#draw)|Kaynak dikdörtgenden bir bit eşlemi hedef dikdörtgenin içine kopyalar. `Draw`gerekirse hedef dikdörtgenin boyutlarına uyacak şekilde bit eşlemi uzatır veya sıkıştırır ve alfa karıştırma ve saydam renkleri işler.|
|[CImage::GetBits](#getbits)|Bit eşleminin gerçek piksel değerlerine işaretçi alır.|
|[CImage::GetBPP](#getbpp)|Piksel başına bitleri alır.|
|[CImage::GetColorTable](#getcolortable)|Renk tablosundaki bir dizi girişten kırmızı, yeşil, mavi (RGB) renk değerlerini alır.|
|[CImage::GetDC](#getdc)|Geçerli bit eşleminin seçildiği aygıt bağlamını alır.|
|[CImage::GetExporterFilterString](#getexporterfilterstring)|Kullanılabilir resim biçimlerini ve açıklamalarını bulur.|
|[CImage::GetHeight](#getheight)|Geçerli görüntünün yüksekliğini piksellerde alır.|
|[CImage::GetImporterFilterString](#getimporterfilterstring)|Kullanılabilir resim biçimlerini ve açıklamalarını bulur.|
|[CImage::GetMaxColorTableEntries](#getmaxcolortableentries)|Renk tablosundaki en fazla giriş sayısını alır.|
|[CImage::GetPitch](#getpitch)|Geçerli görüntünün perdesini baytlar halinde alır.|
|[CImage::GetPixel](#getpixel)|*x* ve *y*tarafından belirtilen pikselin rengini alır.|
|[CImage::GetPixelAddress](#getpixeladdress)|Belirli bir pikselin adresini alır.|
|[CImage::GetTransparentColor](#gettransparentcolor)|Renk tablosundaki saydam rengin konumunu alır.|
|[CImage::GetWidth](#getwidth)|Geçerli görüntünün piksellerde genişliğini alır.|
|[CImage::IsDIBSection](#isdibsection)|Ekteki bit eşleminin BIR DIB bölümü olup olmadığını belirler.|
|[CImage::IsIndexed](#isindexed)|Bitmap'in renklerinin dizine eklenmiş bir paletle eşlendiğini gösterir.|
|[CImage::Isnull](#isnull)|Kaynak bit eşleminin şu anda yüklenip yüklenmediğini gösterir.|
|[CImage::IsTransparencyDestekli](#istransparencysupported)|Uygulamanın saydam bit eşlemlerini destekleyip desteklemediğini gösterir.|
|[CImage::Yük](#load)|Belirtilen dosyadan görüntü yükler.|
|[CImage::loadfromkaynak](#loadfromresource)|Belirtilen kaynaktan görüntü yükler.|
|[CImage::MaskBlt](#maskblt)|Belirtilen maske ve raster işlemini kullanarak kaynak ve hedef bit eşlemlerinin renk verilerini birleştirir.|
|[CImage::PlgBlt](#plgblt)|Kaynak aygıt bağlamında dikdörtgenden hedef aygıt bağlamında paralelkenara bit blok aktarım gerçekleştirir.|
|[CImage::ReleaseDC](#releasedc)|[CImage::GetDC](#getdc)ile alınan aygıt bağlamını yayımlar.|
|[CImage::ReleaseGDIPlus](#releasegdiplus)|GDI+ tarafından kullanılan kaynakları salar. Genel `CImage` bir nesne tarafından oluşturulan özgür kaynaklara çağrılmalıdır.|
|[CImage::Kaydet](#save)|Görüntüyü belirtilen tür olarak kaydeder. `Save`görüntü seçeneklerini belirtemez.|
|[CImage::SetColorTable](#setcolortable)|DIB bölümünün renk tablosundaki bir dizi girişte kırmızı, yeşil, mavi RGB renk değerlerini ayarlar.|
|[CImage::SetPixel](#setpixel)|Belirtilen koordinatlarda pikseli belirtilen renge ayarlar.|
|[CImage::SetPixelIndexed](#setpixelindexed)|Belirtilen koordinatlarda pikseli paletin belirtilen dizininde renge ayarlar.|
|[CImage::SetPixelRGB](#setpixelrgb)|Belirtilen koordinatlarda pikseli belirtilen kırmızı, yeşil, mavi (RGB) değerine ayarlar.|
|[CImage::SetTransparentColor](#settransparentcolor)|Saydam olarak kabul edilecek renk dizini ayarlar. Paletteki yalnızca bir renk saydam olabilir.|
|[CImage::StretchBlt](#stretchblt)|Kaynak dikdörtgenden bir bit eşemi hedef dikdörtgenin içine kopyalar, gerekirse hedef dikdörtgenin boyutlarına uyacak şekilde bit eşlemi uzatır veya sıkıştırır.|
|[CImage::TransparentBlt](#transparentblt)|Kaynak aygıt bağlamından bu geçerli aygıt bağlamına saydam renkle bir bit eşlemi kopyalar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CImage::operatör HBITMAP](#operator_hbitmap)|Nesneye bağlı Windows tutamacını `CImage` döndürür.|

## <a name="remarks"></a>Açıklamalar

`CImage`aygıtdan bağımsız bitmap (DIB) bölümleri olup olmadığını bit eşlemler alır; ancak, [Oluştur](#create) veya [CImage::Yalnızca](#load) DIB bölümleriyle yükleyin'i kullanabilirsiniz. Ekle'yi kullanarak bir nesneye DIB `CImage` olmayan [Attach](#attach)bir bölüm bit eşlemi ekleyebilirsiniz, ancak sonra yalnızca DIB bölüm bit eşlemlerini destekleyen aşağıdaki `CImage` yöntemleri kullanamazsınız:

- [GetBits](#getbits)

- [GetColorTable](#getcolortable)

- [GetMaxColorTableEntries](#getmaxcolortableentries)

- [GetPitch](#getpitch)

- [GetPixelAddress](#getpixeladdress)

- [IsIndexed](#isindexed)

- [SetColorTable](#setcolortable)

Ekli bir bit eşleminin DIB bölümü olup olmadığını belirlemek için [IsDibSection'ı](#isdibsection)arayın.

> [!NOTE]
> Visual Studio .NET 2003'te bu sınıf, `CImage` oluşturulan nesne sayısının sayısını tutar. Sayım 0'a gittiğinde, işlev `GdiplusShutdown` GDI+ tarafından kullanılan kaynakları serbest bırakmak için otomatik olarak çağrılır. Bu, DL'ler tarafından doğrudan veya dolaylı olarak oluşturulan nesnelerin `CImage` her `GdiplusShutdown` zaman düzgün `DllMain`bir şekilde yok edilmesini ve 'den çağrılmamasını sağlar.

> [!NOTE]
> DLL'de genel `CImage` nesnelerin kullanılması önerilmez. Bir DLL'de `CImage` genel bir nesne kullanmanız gerekiyorsa, GDI+ tarafından kullanılan kaynakları açıkça serbest bırakmak için [CImage:ReleaseGDIPlus'ı](#releasegdiplus) arayın.

`CImage`yeni bir [CDC'ye](../../mfc/reference/cdc-class.md)seçilemez. `CImage`görüntü için kendi HDC'sini oluşturur. Bir HBITMAP aynı anda yalnızca bir HDC'ye seçilebildiği `CImage` için, hbitmap ile ilişkili başka bir HDC'ye seçilemez. Bir CDC gerekiyorsa, HDC almak `CImage` ve CDC [vermek::FromHandle](../../mfc/reference/cdc-class.md#fromhandle).

## <a name="example"></a>Örnek

```cpp
// Get a CDC for the image
CDC* pDC = CDC::FromHandle(m_myImage.GetDC());

// Use pDC here
pDC->Rectangle(0, 40, 100, 50);
m_myImage.ReleaseDC();
```

Bir MFC projesinde kullandığınızda, `CImage` projenizdeki hangi üye işlevlerin bir [CBitmap](../../mfc/reference/cbitmap-class.md) nesnesine işaretçi beklediğini unutmayın. `CImage` [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu)gibi böyle bir işlevle kullanmak istiyorsanız, [CBitmap kullanın::FromHandle](../../mfc/reference/cbitmap-class.md#fromhandle), `CImage` HBITMAP geçmek `CBitmap*`ve döndürülen kullanın.

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

Aracılığıyla, `CImage`bir DIB bölümünün gerçek bitlerine erişebilirsiniz. Bir `CImage` nesneyi daha önce Win32 HBITMAP veya DIB bölümünü kullandığınız her yerde kullanabilirsiniz.

MFC `CImage` veya ATL'den kullanabilirsiniz.

> [!NOTE]
> Bir proje yi `CImage`kullanarak oluşturduğunuzda, `CString` *atlimage.h'yi*eklemeden önce tanımlamanız gerekir. Projenizde MFC olmadan ATL *kullanıyorsa, atlimage.h*eklemeden önce *atlstr.h'yi* ekleyin. Projeniz MFC kullanıyorsa (veya MFC destekli bir ATL projesiyse), *atlimage.h*eklemeden önce *afxstr.h'yi* ekleyin.<br/>
> <br/>
> Aynı şekilde, *atlimpl.cpp*eklemeden önce *atlimage.h* eklemeniz gerekir. Bunu kolayca başarmak için *pch.h* (Visual Studio 2017 ve daha önce*stdafx.h)* içinde *atlimage.h'yi* ekleyin.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlimage.h

## <a name="cimagealphablend"></a><a name="alphablend"></a>CImage::AlphaBlend

Saydam veya yarı saydam piksellere sahip bit eşlemleri görüntüler.

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
Hedef aygıt bağlamına işle.

*xDest*<br/>
X-koordinat, mantıksal birimler, hedef dikdörtgenin sol üst köşesinde.

*yDest*<br/>
Y-koordinat, mantıksal birimler, hedef dikdörtgenin sol üst köşesinde.

*bSrcAlpha*<br/>
Tüm kaynak bit haritasında kullanılacak bir alfa saydamlık değeri. Varsayılan 0xff (255), görüntünüzün opak olduğunu ve yalnızca piksel başına alfa değerlerini kullanmak istediğinizi varsayar.

*bBlendOp*<br/>
Kaynak ve hedef bit eşlemleri için alfa karıştırma işlevi, tüm kaynak bit haritasına uygulanacak küresel alfa değeri ve kaynak bit eşlemi için bilgileri biçimlendirme. Kaynak ve hedef karışım işlevleri şu anda AC_SRC_OVER ile sınırlıdır.

*pointDest*<br/>
Hedef dikdörtgenin sol üst köşesini mantıksal birimler halinde tanımlayan bir [POINT](/previous-versions/dd162805\(v=vs.85\)) yapısına yapılan başvuru.

*nDestGenişliği*<br/>
Hedef dikdörtgenin mantıksal birimleriyle genişliği.

*nDestYükseklik*<br/>
Hedef dikdörtgenin mantıksal birimleriyle yüksekliği.

*xSrc*<br/>
Kaynak dikdörtgenin sol üst köşesinin mantıksal x-koordinatı.

*ySrc*<br/>
Kaynak dikdörtgenin sol üst köşesinin mantıksal koordinatı.

*nSrcGenişlik*<br/>
Kaynak dikdörtgenin mantıksal birimleriyle genişliği.

*nSrcYükseklik*<br/>
Mantıksal birimlerde, kaynak dikdörtgenin yüksekliği.

*rektDest*<br/>
Hedefi tanımlayan bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısına başvuru.

*rectSrc*<br/>
Kaynağı tanımlayan `RECT` bir yapıya başvuru.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Alfa karışımı bit eşlemleri piksel başına renk karıştırmayı destekler.

*bBlendOp* AC_SRC_OVER varsayılan olarak ayarlandığında, kaynak bit eşlemi kaynak piksellerin alfa değerlerini temel alan hedef bit eşlemi üzerine yerleştirilir.

## <a name="cimageattach"></a><a name="attach"></a>CImage::Ekle

Bir nesneye *hBitmap* ataşıyor. `CImage`

```
void Attach(HBITMAP hBitmap, DIBOrientation eOrientation = DIBOR_DEFAULT) throw();
```

### <a name="parameters"></a>Parametreler

*Hbıtmap*<br/>
HBITMAP için bir tanıtıcı.

*eOryantasyon*<br/>
Bit eşleninin yönünü belirtir. Aşağıdakilerden biri olabilir:

- DIBOR_DEFAULT Bitmap'in yönü işletim sistemi tarafından belirlenir.

- DIBOR_BOTTOMUP Bit haritasının satırları ters sıradadır. Bu, [CImage::GetBits](#getbits) bitmap arabelleği ve CImage sonuna yakın bir işaretçi döndürmek için neden [olur::GetPitch](#getpitch) negatif bir sayı döndürmek için.

- DIBOR_TOPDOWN Bit eşleminin satırları üstten alta sırayla dır. Bu, [CImage::GetBits'in](#getbits) bir işaretçiyi biteş arabelleği ve CImage'in ilk baytına döndürmesine neden [olur::GetPitch](#getpitch) pozitif bir sayı döndürür.

### <a name="remarks"></a>Açıklamalar

Biteş, DIB olmayan bir bölüm bit eşlemi veya DIB kesit bit eşlemi olabilir. Yalnızca DIB bölüm bit eşlemleriyle kullanabileceğiniz yöntemlerin listesi için [Bkz.](#isdibsection)

## <a name="cimagebitblt"></a><a name="bitblt"></a>CImage::BitBlt

Kaynak aygıt bağlamından bu geçerli aygıt bağlamına bir bit eşlemi kopyalar.

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
Hedef dikdörtgenin sol üst köşesinin mantıksal x-koordinatı.

*yDest*<br/>
Hedef dikdörtgenin sol üst köşesinin mantıksal koordinatı.

*dwROP*<br/>
Yapılacak raster operasyonu. Raster-işlem kodları, hedefi oluşturmak için kaynağın, hedefin ve desenin (şu anda seçili fırça tarafından tanımlandığı şekilde) bitlerinin tam olarak nasıl birleştirilecek olduğunu tanımlar. Diğer raster işlem kodlarının ve açıklamalarının listesi için Windows SDK'daki [BitBlt'e](/windows/win32/api/wingdi/nf-wingdi-bitblt) bakın.

*pointDest*<br/>
Hedef dikdörtgenin sol üst köşesini gösteren bir [POINT](/previous-versions/dd162805\(v=vs.85\)) yapısı.

*nDestGenişliği*<br/>
Hedef dikdörtgenin mantıksal birimleriyle genişliği.

*nDestYükseklik*<br/>
Hedef dikdörtgenin mantıksal birimleriyle yüksekliği.

*xSrc*<br/>
Kaynak dikdörtgenin sol üst köşesinin mantıksal x-koordinatı.

*ySrc*<br/>
Kaynak dikdörtgenin sol üst köşesinin mantıksal koordinatı.

*rektDest*<br/>
Hedef dikdörtgeni gösteren bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısı.

*noktaSrc*<br/>
Kaynak `POINT` dikdörtgenin sol üst köşesini gösteren bir yapı.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK'daki [BitBlt'e](/windows/win32/api/wingdi/nf-wingdi-bitblt) bakın.

## <a name="cimagecimage"></a><a name="cimage"></a>CImage::CImage

Bir `CImage` nesne inşa eder.

```
CImage() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesneyi oluşturduktan sonra [Oluştur,](#create) [Yükle](#load), [LoadFromResource](#loadfromresource)veya nesneye bit eşlemi eklemek için [ekle'yi](#attach) arayın.

**Not** Visual Studio'da bu sınıf, oluşturulan `CImage` nesne sayısının sayısını tutar. Sayım 0'a gittiğinde, işlev `GdiplusShutdown` GDI+ tarafından kullanılan kaynakları serbest bırakmak için otomatik olarak çağrılır. Bu, DL'ler tarafından doğrudan veya dolaylı olarak oluşturulan nesnelerin `CImage` her `GdiplusShutdown` zaman doğru şekilde yok edilmesini ve DllMain'den çağrılmamasını sağlar.

DLL'de genel `CImage` nesnelerin kullanılması önerilmez. Bir DLL'de `CImage` genel bir nesne kullanmanız gerekiyorsa, GDI+ tarafından kullanılan kaynakları açıkça serbest bırakmak için [CImage:ReleaseGDIPlus'ı](#releasegdiplus) arayın.

## <a name="cimagecreate"></a><a name="create"></a>CImage::Oluştur

Bir `CImage` bit eşlemi oluşturur ve daha `CImage` önce oluşturulmuş nesneye bağlar.

```
BOOL Create(
    int nWidth,
    int nHeight,
    int nBPP,
    DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Parametreler

*Nwidth*<br/>
Bit eşleminin `CImage` piksel genişliği.

*Nheight*<br/>
Bit eşleninin `CImage` yüksekliği, piksel olarak. *nHeight* pozitifse, bit eşlemi aşağıdan yukarıya bir DIB ve kökeni sol alt köşedir. *nHeight* negatifse, biteşe yukarıdan aşağıya BIR DIB ve kökeni sol üst köşedir.

*nBPP*<br/>
Bit haritasındaki piksel başına bit sayısı. Genellikle 4, 8, 16, 24 veya 32. Tek renkli bit eşlemler veya maskeler için 1 olabilir.

*Dwflags*<br/>
Bitmap nesnesinin alfa kanalı olup olmadığını belirtir. Aşağıdaki değerlerin sıfır veya daha fazlasının bir leşimi olabilir:

- *AlphaChannel oluşturma* Yalnızca *nBPP* 32 ve *eCompression* BI_RGB ise kullanılabilir. Belirtilirse, oluşturulan görüntü, her pikselin 4'üncü baytında depolanan (alfa olmayan 32 bit görüntüde kullanılmayan) her piksel için bir alfa (saydamlık) değerine sahiptir. Bu alfa kanalı [CImage::AlphaBlend'i](#alphablend)ararken otomatik olarak kullanılır.

> [!NOTE]
> [CImage::Draw'](#draw)a yapılan aramalarda, alfa kanallı görüntüler otomatik olarak hedefe alfa ile karıştırılır.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

## <a name="cimagecreateex"></a><a name="createex"></a>CImage::CreateEx

Bir `CImage` bit eşlemi oluşturur ve daha `CImage` önce oluşturulmuş nesneye bağlar.

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

*Nwidth*<br/>
Bit eşleminin `CImage` piksel genişliği.

*Nheight*<br/>
Bit eşleninin `CImage` yüksekliği, piksel olarak. *nHeight* pozitifse, bit eşlemi aşağıdan yukarıya bir DIB ve kökeni sol alt köşedir. *nHeight* negatifse, biteşe yukarıdan aşağıya BIR DIB ve kökeni sol üst köşedir.

*nBPP*<br/>
Bit haritasındaki piksel başına bit sayısı. Genellikle 4, 8, 16, 24 veya 32. Tek renkli bit eşlemler veya maskeler için 1 olabilir.

*eSıkıştırma*<br/>
Sıkıştırılmış aşağıdan yukarıya bit eşlemi için sıkıştırma türünü belirtir (yukarıdan aşağıya DIB'ler sıkıştırılamaz). Aşağıdaki değerlerden biri olabilir:

- BI_RGB Biçimi sıkıştırılmamıştır. Arama `CImage::CreateEx` yaparken bu değeri belirtme, `CImage::Create`aramaya eşdeğerdir.

- BI_BITFIELDS Biçim sıkıştırılmamıştır ve renk tablosu, her pikselin sırasıyla kırmızı, yeşil ve mavi bileşenlerini belirten üç DWORD renk maskesinden oluşur. Bu, 16 ve 32-bpp bit eşlemlerle kullanıldığında geçerlidir.

*pdwBitfields*<br/>
Yalnızca *eSıkıştırma* BI_BITFIELDS ayarlanmışsa kullanılır, aksi takdirde NULL olmalıdır. Her pikselin hangi bitlerinin rengin kırmızı, yeşil ve mavi bileşenleri için kullanıldığını belirten üç DWORD bit maskesi dizisine işaretçi. Bit alanlarının kısıtlamaları hakkında daha fazla bilgi için Windows SDK'daki [BITMAPINFOHEADER'a](/previous-versions//dd183376\(v=vs.85\)) bakın.

*Dwflags*<br/>
Bitmap nesnesinin alfa kanalı olup olmadığını belirtir. Aşağıdaki değerlerin sıfır veya daha fazlasının bir leşimi olabilir:

- *AlphaChannel oluşturma* Yalnızca *nBPP* 32 ve *eCompression* BI_RGB ise kullanılabilir. Belirtilirse, oluşturulan görüntü, her pikselin 4'üncü baytında depolanan (alfa olmayan 32 bit görüntüde kullanılmayan) her piksel için bir alfa (saydamlık) değerine sahiptir. Bu alfa kanalı [CImage::AlphaBlend'i](#alphablend)ararken otomatik olarak kullanılır.

   > [!NOTE]
   > [CImage::Draw'](#draw)a yapılan aramalarda, alfa kanallı görüntüler otomatik olarak hedefe alfa ile karıştırılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa DOĞRU. Aksi takdirde YANLIŞ.

### <a name="example"></a>Örnek

Aşağıdaki örnek, her pikseli kodlamak için 16 bit kullanarak 100x100 piksel bit eşlemi oluşturur. Belirli bir 16 bit pikselde, 0-3 bitleri kırmızı bileşeni, bitleri 4-7 yeşili ve bit8-11 maviyi kodlar. Kalan 4 bit kullanılmaz.

```cpp
DWORD adwBitmasks[3] = { 0x0000000f, 0x000000f0, 0x00000f00 };
m_myImage.CreateEx(100, 100, 16, BI_BITFIELDS, adwBitmasks, 0);
```

## <a name="cimagedestroy"></a><a name="destroy"></a>CImage::Destroy

Bit eşlemi `CImage` nesneden ayırır ve bit eşlemi yok eder.

```
void Destroy() throw();
```

## <a name="cimagedetach"></a><a name="detach"></a>CImage::Detach

Bir `CImage` nesneden bir bit eşlemi ayırır.

```
HBITMAP Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bit eşlemi ayrılmış bir tutamaç veya bit eşlemi eklenmişse NULL.

## <a name="cimagedraw"></a><a name="draw"></a>CImage::Draw

Kaynak aygıt bağlamından geçerli aygıt bağlamına bir bit eşlemi kopyalar.

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
Hedef aygıt bağlamına bir tanıtıcı.

*xDest*<br/>
X-koordinat, mantıksal birimler, hedef dikdörtgenin sol üst köşesinde.

*yDest*<br/>
Y-koordinat, mantıksal birimler, hedef dikdörtgenin sol üst köşesinde.

*nDestGenişliği*<br/>
Hedef dikdörtgenin mantıksal birimleriyle genişliği.

*nDestYükseklik*<br/>
Hedef dikdörtgenin mantıksal birimleriyle yüksekliği.

*xSrc*<br/>
X-koordinat, mantıksal birimler, kaynak dikdörtgenin sol üst köşesinde.

*ySrc*<br/>
Y-koordinat, mantıksal birimler, kaynak dikdörtgenin sol üst köşesinde.

*nSrcGenişlik*<br/>
Kaynak dikdörtgenin mantıksal birimleriyle genişliği.

*nSrcYükseklik*<br/>
Mantıksal birimlerde, kaynak dikdörtgenin yüksekliği.

*rektDest*<br/>
Hedefi tanımlayan bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısına başvuru.

*rectSrc*<br/>
Kaynağı tanımlayan `RECT` bir yapıya başvuru.

*pointDest*<br/>
Hedef dikdörtgenin sol üst köşesini mantıksal birimler halinde tanımlayan bir [POINT](/previous-versions/dd162805\(v=vs.85\)) yapısına yapılan başvuru.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`Draw`görüntü saydam bir renk veya alfa kanalı içermediği sürece [StretchBlt](#stretchblt)ile aynı işlemi gerçekleştirir. Bu durumda, `Draw` gerektiğinde [TransparentBlt](#transparentblt) veya [AlphaBlend](#alphablend) ile aynı işlemi gerçekleştirir.

Kaynak dikdörtgen `Draw` belirtmeyin sürümleri için, tüm kaynak görüntü varsayılandır. Bunun sürümü `Draw` için hedef dikdörtgen için bir boyut belirtmez, kaynak görüntünün boyutu varsayılandır ve hiçbir germe veya küçültme oluşur.

## <a name="cimagegetbits"></a><a name="getbits"></a>CImage::GetBits

Bit haritasında belirli bir pikselin gerçek bit değerlerine işaretçi alır.

```
void* GetBits() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bitmap arabelleği için bir işaretçi. Bit eşlem aşağıdan yukarıya bir DIB ise, işaretçi arabelleğe yakın işaret eder. Biteş yukarıdan aşağıya BIR DIB ise, işaretçi arabelleğeilk baytını işaret eder.

### <a name="remarks"></a>Açıklamalar

Bu işaretçiyi kullanarak, [GetPitch](#getpitch)tarafından döndürülen değerle birlikte, görüntüdeki pikselleri tek tek bulabilir ve değiştirebilirsiniz.

> [!NOTE]
> Bu yöntem yalnızca DIB bölüm bit eşlemlerini destekler; sonuç olarak, bir `CImage` nesnenin piksellerine, dib bölümünün piksellerine yaptığınız gibi erişebilirsiniz. Döndürülen işaretçi, konumdaki pikseli işaret eder (0, 0).

## <a name="cimagegetbpp"></a><a name="getbpp"></a>CImage::GetBPP

Piksel başına bit değerini alır.

```
int GetBPP() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Piksel başına bit sayısı.

### <a name="remarks"></a>Açıklamalar

Bu değer, her pikseli tanımlayan bit sayısını ve bit eşlemindeki en büyük renk sayısını belirler.

Piksel başına bitgenellikle 1, 4, 8, 16, 24 veya 32'dir. Bu `biBitCount` değer hakkında daha fazla bilgi için Windows SDK'daki [BITMAPINFOHEADER](/previous-versions//dd183376\(v=vs.85\)) üyesine bakın.

## <a name="cimagegetcolortable"></a><a name="getcolortable"></a>CImage::GetColorTable

DIB bölümünün paletindeki bir dizi girişten kırmızı, yeşil, mavi (RGB) renk değerlerini alır.

```
void GetColorTable(
    UINT iFirstColor,
    UINT nColors,
    RGBQUAD* prgbColors) const throw();
```

### <a name="parameters"></a>Parametreler

*iFirstColor*<br/>
Almak için ilk girişin renk tablosu dizini.

*nColors*<br/>
Alınacak renk tablosu girişlerinin sayısı.

*prgbColors*<br/>
Renk tablosu girişlerini almak için [RGBQUAD](/windows/win32/api/wingdi/ns-wingdi-rgbquad) yapıları dizisini işaretçi.

## <a name="cimagegetdc"></a><a name="getdc"></a>CImage::GetDC

Şu anda içinde görüntü seçilen aygıt bağlamını alır.

```
HDC GetDC() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Aygıt bağlamına bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Her arama `GetDC`için , [ReleaseDC](#releasedc)için bir sonraki çağrı olması gerekir.

## <a name="cimagegetexporterfilterstring"></a><a name="getexporterfilterstring"></a>CImage::GetExporterFilterString

Görüntüleri kaydetmek için kullanılabilen görüntü biçimlerini bulur.

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
Bir `CSimpleString` nesneye başvuru. Daha fazla bilgi için **Açıklamalar'a** bakın.

*aguidFileTypes*<br/>
Her öğe dizedeki dosya türlerinden birine karşılık gelen bir dizi GUIDs. Aşağıdaki *pszAllFilesDescription* örnekte, *aguidFileTypes*[0] GUID_NULL ve kalan dizi değerleri geçerli işletim sistemi tarafından desteklenen görüntü dosyası biçimleridir.

> [!NOTE]
> Sabitlerin tam listesi için Windows SDK'daki **Resim Dosyası Biçim Sabitleri'ne** bakın.

*pszAllFilesDescription*<br/>
Bu parametre NULL değilse, filtre dizesi listenin başında bir ek filtre olacaktır. Bu filtre, açıklaması için *pszAllFilesDescription* geçerli değerine sahip olacak ve listede başka bir ihracatçı tarafından desteklenen herhangi bir uzantı dosyaları kabul eder.

Örneğin:

```cpp
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any exporter.
CImage::GetExporterFilterString(
    strExporters, aguidFileTypes,
_T("All Image Files"));
```

*dwExclude*<br/>
Listeden hangi dosya türlerinin dışlanacağı belirtilirken bit bayrakları kümesi. İzin verilebilen bayraklar şunlardır:

- `excludeGIF`= 0x01 GIF dosyalarını hariç tutar.

- `excludeBMP`= 0x02 BMP (Windows Bitmap) dosyalarını dışlar.

- `excludeEMF`= 0x04 EMF (Geliştirilmiş Metadosya) dosyalarını hariç tutar.

- `excludeWMF`= 0x08 WMF (Windows Metafile) dosyalarını hariç tutar.

- `excludeJPEG`= 0x10 JPEG dosyalarını hariç tutar.

- `excludePNG`= 0x20 PNG dosyalarını hariç tutar.

- `excludeTIFF`= 0x40 TIFF dosyalarını hariç tutar.

- `excludeIcon`= 0x80 ICO (Windows Simgesi) dosyalarını hariç tutar.

- `excludeOther`= 0x8000000yukarıda listelenmemiş diğer dosya türünü hariç tutar.

- `excludeDefaultLoad`= 0 Yük için, tüm dosya türleri varsayılan olarak dahil edilir

- `excludeDefaultSave` = `excludeIcon &#124; excludeEMF &#124; excludeWMF`Kaydetmek için, genellikle özel gereksinimleri olduğundan bu dosyalar varsayılan olarak hariç tutulur.

*chSeparator*<br/>
Görüntü biçimleri arasında kullanılan ayırıcı. Daha fazla bilgi için **Açıklamalar'a** bakın.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Dosya Olarak Kaydet iletişim kutusunda ki kullanılabilir görüntü biçimlerinin dosya uzantılarını ortaya çıkarmak için ortaya çıkan biçim dizesini MFC [CFileDialog](../../mfc/reference/cfiledialog-class.md) nesnenize geçirebilirsiniz.

Parametre *strExporter* biçimi vardır:

dosya açıklaması0 \*&#124;.ext0&#124;\*filedescription1&#124;.ext1&#124;... dosya *n* açıklaması \*n&#124;.ext *n*&#124;&#124;

burada '&#124;' tarafından `chSeparator`belirtilen ayırıcı karakterdir. Örneğin:

`"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`

Bu dizeyi bir MFC `CFileDialog` nesnesine geçirirseniz varsayılan ayırıcı '&#124;' kullanın. Bu dizeyi ortak bir Dosya Kaydet iletişim kutusuna geçirirseniz null ayırıcı '\0' kullanın.

## <a name="cimagegetheight"></a><a name="getheight"></a>CImage::GetHeight

Bir görüntünün yüksekliğini, piksel olarak alır.

```
int GetHeight() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir görüntünün piksel yüksekliği.

## <a name="cimagegetimporterfilterstring"></a><a name="getimporterfilterstring"></a>CImage::GetImporterFilterString

Görüntüleri yüklemek için kullanılabilen görüntü biçimlerini bulur.

```
static HRESULT GetImporterFilterString(
    CSimpleString& strImporters,
    CSimpleArray<GUID>& aguidFileTypes,
    LPCTSTR pszAllFilesDescription = NULL,
    DWORD dwExclude = excludeDefaultLoad,
    TCHAR chSeparator = _T('|'));
```

### <a name="parameters"></a>Parametreler

*strİthalatçılar*<br/>
Bir `CSimpleString` nesneye başvuru. Daha fazla bilgi için **Açıklamalar'a** bakın.

*aguidFileTypes*<br/>
Her öğe dizedeki dosya türlerinden birine karşılık gelen bir dizi GUIDs. Aşağıdaki *pszAllFilesDescription* örnekte, *aguidFileTypes*[0] kalan dizi değerleri ile GUID_NULL mevcut işletim sistemi tarafından desteklenen görüntü dosyası biçimleri vardır.

> [!NOTE]
> Sabitlerin tam listesi için Windows SDK'daki **Resim Dosyası Biçim Sabitleri'ne** bakın.

*pszAllFilesDescription*<br/>
Bu parametre NULL değilse, filtre dizesi listenin başında bir ek filtre olacaktır. Bu filtre, açıklaması için *pszAllFilesDescription* geçerli değerine sahip olacak ve listede başka bir ihracatçı tarafından desteklenen herhangi bir uzantı dosyaları kabul eder.

Örneğin:

```cpp
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any importer.
CImage::GetImporterFilterString(
    strImporters, aguidFileTypes,
_T("All Image Files"));
```

*dwExclude*<br/>
Listeden hangi dosya türlerinin dışlanacağı belirtilirken bit bayrakları kümesi. İzin verilebilen bayraklar şunlardır:

- `excludeGIF`= 0x01 GIF dosyalarını hariç tutar.

- `excludeBMP`= 0x02 BMP (Windows Bitmap) dosyalarını dışlar.

- `excludeEMF`= 0x04 EMF (Geliştirilmiş Metadosya) dosyalarını hariç tutar.

- `excludeWMF`= 0x08 WMF (Windows Metafile) dosyalarını hariç tutar.

- `excludeJPEG`= 0x10 JPEG dosyalarını hariç tutar.

- `excludePNG`= 0x20 PNG dosyalarını hariç tutar.

- `excludeTIFF`= 0x40 TIFF dosyalarını hariç tutar.

- `excludeIcon`= 0x80 ICO (Windows Simgesi) dosyalarını hariç tutar.

- `excludeOther`= 0x8000000yukarıda listelenmemiş diğer dosya türünü hariç tutar.

- `excludeDefaultLoad`= 0 Yük için, tüm dosya türleri varsayılan olarak dahil edilir

- `excludeDefaultSave` = `excludeIcon &#124; excludeEMF &#124; excludeWMF`Kaydetmek için, genellikle özel gereksinimleri olduğundan bu dosyalar varsayılan olarak hariç tutulur.

*chSeparator*<br/>
Görüntü biçimleri arasında kullanılan ayırıcı. Daha fazla bilgi için **Açıklamalar'a** bakın.

### <a name="remarks"></a>Açıklamalar

**Dosya Aç** iletişim kutusunda ki kullanılabilir görüntü biçimlerinin dosya uzantılarını ortaya çıkarmak için ortaya çıkan biçim dizesini MFC [CFileDialog](../../mfc/reference/cfiledialog-class.md) nesnenize geçirebilirsiniz.

*StrImporter* parametresi biçimine sahiptir:

dosya açıklaması0 \*&#124;.ext0&#124;\*filedescription1&#124;.ext1&#124;... dosya *n* açıklaması \*n&#124;.ext *n*&#124;&#124;

burada '&#124;' *chSeparator*tarafından belirtilen ayırıcı karakterdir. Örneğin:

`"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`

Bu dizeyi bir MFC `CFileDialog` nesnesine geçirirseniz varsayılan ayırıcı '&#124;' kullanın. Bu dizeyi ortak bir **Dosya Aç** iletişim kutusuna geçirirseniz null ayırıcı '\0' kullanın.

## <a name="cimagegetmaxcolortableentries"></a><a name="getmaxcolortableentries"></a>CImage::GetMaxColorTableEntries

Renk tablosundaki en fazla giriş sayısını alır.

```
int GetMaxColorTableEntries() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Renk tablosundaki giriş sayısı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca DIB bölüm bit eşlemlerini destekler.

## <a name="cimagegetpitch"></a><a name="getpitch"></a>CImage::GetPitch

Görüntünün perdesini alır.

```
int GetPitch() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Görüntünün perdesi. İade değeri negatifse, bit eşlemi aşağıdan yukarıya bir DIB ve kökeni sol alt köşedir. İade değeri pozitifse, bit eşlemi yukarıdan aşağıya BIR DIB ve kökeni sol üst köşedir.

### <a name="remarks"></a>Açıklamalar

Adım, bir bitmap satırının başlangıcını ve bir sonraki bitmap satırının başlangıcını temsil eden iki bellek adresi arasındaki mesafedir. Perde bayt cinsinden ölçüldüğünde, görüntünün perdesi piksel biçimini belirlemenize yardımcı olur. Pitch da bit map için ayrılmış ek bellek içerebilir.

Görüntünün tek tek piksellerini bulmak için `GetPitch` [GetBits](#getbits) ile kullanın.

> [!NOTE]
> Bu yöntem yalnızca DIB bölüm bit eşlemlerini destekler.

## <a name="cimagegetpixel"></a><a name="getpixel"></a>CImage::GetPixel

*X* ve *y*tarafından belirtilen konumdapikselin rengini alır.

```
COLORREF GetPixel(int x, int y) const throw();
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Pikselin x-koordinatı.

*Y*<br/>
Pikselin y-koordinatı.

### <a name="return-value"></a>Dönüş Değeri

Pikselin kırmızı, yeşil, mavi (RGB) değeri. Piksel geçerli kırpma bölgesinin dışındaysa, iade değeri CLR_INVALID.

## <a name="cimagegetpixeladdress"></a><a name="getpixeladdress"></a>CImage::GetPixelAddress

Pikselin tam adresini alır.

```
void* GetPixelAddress(int x, int y) throw();
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Pikselin x-koordinatı.

*Y*<br/>
Pikselin y-koordinatı.

### <a name="remarks"></a>Açıklamalar

Adres, bir pikselin koordinatlarına, bit eşleninin perdesine ve piksel başına bitlere göre belirlenir.

Piksel başına 8 bitten az olan biçimler için bu yöntem, pikseli içeren baytın adresini döndürür. Örneğin, görüntü biçiminizde piksel başına 4 `GetPixelAddress` bit varsa, bayttaki ilk pikselin adresini döndürür ve bayt başına 2 piksel hesaplamanız gerekir.

> [!NOTE]
> Bu yöntem yalnızca DIB bölüm bit eşlemlerini destekler.

## <a name="cimagegettransparentcolor"></a><a name="gettransparentcolor"></a>CImage::GetTransparentColor

Renk paletindeki saydam rengin dizine eklenmiş konumunu alır.

```
LONG GetTransparentColor() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Saydam renk dizini.

## <a name="cimagegetwidth"></a><a name="getwidth"></a>CImage::GetWidth

Bir görüntünün genişliğini, piksel olarak alır.

```
int GetWidth() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bit eşleminin piksel genişliği.

## <a name="cimageisdibsection"></a><a name="isdibsection"></a>CImage::IsDIBSection

Ekteki bit eşleminin BIR DIB bölümü olup olmadığını belirler.

```
bool IsDIBSection() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ekli bitmap bir DIB bölümü ise DOĞRU. Aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bit eşlem bir DIB bölümü değilse, yalnızca `CImage` DIB bölüm biteşlerini destekleyen aşağıdaki yöntemleri kullanamazsınız:

- [GetBits](#getbits)

- [GetColorTable](#getcolortable)

- [GetMaxColorTableEntries](#getmaxcolortableentries)

- [GetPitch](#getpitch)

- [GetPixelAddress](#getpixeladdress)

- [IsIndexed](#isindexed)

- [SetColorTable](#setcolortable)

## <a name="cimageisindexed"></a><a name="isindexed"></a>CImage::IsIndexed

Bitmap piksellerinin bir renk paletine eşlenip eşlenmediğini belirler.

```
bool IsIndexed() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Endekslenmişse DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, yalnızca bit eşlemi 8 bit (256 renk) veya daha azsa TRUE döndürür.

> [!NOTE]
> Bu yöntem yalnızca DIB bölüm bit eşlemlerini destekler.

## <a name="cimageisnull"></a><a name="isnull"></a>CImage::Isnull

Bit eşleminin şu anda yüklenip yüklenmeyişolduğunu belirler.

```
bool IsNull() const throw();
```

### <a name="remarks"></a>Açıklamalar

Bit eşlemi şu anda yüklenmiyorsa, bu yöntem TRUE döndürür; aksi takdirde YANLIŞ.

## <a name="cimageistransparencysupported"></a><a name="istransparencysupported"></a>CImage::IsTransparencyDestekli

Uygulamanın saydam bit eşlemlerini destekleyip desteklemediğini gösterir.

```
static BOOL IsTransparencySupported() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli platform saydamlığı destekliyorsa sıfıra inme. Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İade değeri sıfır değilse ve saydamlık desteklenirse, [AlphaBlend,](#alphablend) [TransparentBlt](#transparentblt)veya [Draw'a](#draw) yapılan bir çağrı saydam renkleri işler.

## <a name="cimageload"></a><a name="load"></a>CImage::Yük

Bir görüntü yükler.

```
HRESULT Load(LPCTSTR pszFileName) throw();
HRESULT Load(IStream* pStream) throw();
```

### <a name="parameters"></a>Parametreler

*pszFileName*<br/>
Yüklenmesi gereken görüntü dosyasının adını içeren bir dize işaretçisi.

*pStream*<br/>
Yüklenmesi gereken resim dosyasının adını içeren bir akışa işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

*pszFileName* veya *pStream*tarafından belirtilen görüntüyü yükler.

Geçerli görüntü türleri BMP, GIF, JPEG, PNG ve TIFF'dir.

## <a name="cimageloadfromresource"></a><a name="loadfromresource"></a>CImage::loadfromkaynak

BITMAP kaynağından görüntü yükler.

```
void LoadFromResource(
    HINSTANCE hInstance,
    LPCTSTR pszResourceName) throw();

void LoadFromResource(
    HINSTANCE hInstance,
    UINT nIDResource) throw();
```

### <a name="parameters"></a>Parametreler

*Hınstance*<br/>
Yüklenecek görüntüyü içeren modülün bir örneğine işleyin.

*pszResourceName*<br/>
Yüklenmesi için görüntü içeren kaynağın adını içeren dize için bir işaretçi.

*nIDKaynak*<br/>
Yüklenmesi gereken kaynağın kimliği.

### <a name="remarks"></a>Açıklamalar

Kaynak BITMAP türünde olmalıdır.

## <a name="cimagemaskblt"></a><a name="maskblt"></a>CImage::MaskBlt

Belirtilen maske ve raster işlemini kullanarak kaynak ve hedef bit eşlemlerinin renk verilerini birleştirir.

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
Yürütülebilir kaynağı içeren modülün tutamacı.

*xDest*<br/>
X-koordinat, mantıksal birimler, hedef dikdörtgenin sol üst köşesinde.

*yDest*<br/>
Y-koordinat, mantıksal birimler, hedef dikdörtgenin sol üst köşesinde.

*nDestGenişliği*<br/>
Hedef dikdörtgenin ve kaynak bit eşleminin mantıksal birimleriyle genişliği.

*nDestYükseklik*<br/>
Hedef dikdörtgenin ve kaynak bit haritasının mantıksal birimleriyle yüksekliği.

*xSrc*<br/>
Kaynak bit haritasının sol üst köşesindeki mantıksal x-koordinatı.

*ySrc*<br/>
Kaynak bit haritasının sol üst köşesindeki mantıksal koordinat.

*hbmMaske*<br/>
Tek renkli maske bit eşlemi ile kaynak aygıt bağlamında renk biteşliği ile birleştirin.

*xMaske*<br/>
*hbmMask* parametresi tarafından belirtilen maske biteşliği için yatay piksel ofset.

*yMask*<br/>
*hbmMask* parametresi tarafından belirtilen maske biteşliği için dikey piksel ofset.

*dwROP*<br/>
Yöntemin kaynak ve hedef verilerinin birleşimini denetlemek için kullandığı hem ön plan hem de arka plan tersiyer raster işlem kodlarını belirtir. Arka plan raster işlem kodu, bu değerin yüksek sıralı sözcüğünün yüksek sıralı baytında depolanır; ön plan raster işlem kodu bu değerin yüksek sıralı kelimenin düşük sıralı bayt saklanır; bu değerin düşük sıralı sözcüğü yoksayılır ve sıfır olmalıdır. Bu yöntem bağlamında ön plan ve arka plan tartışması `MaskBlt` için Windows SDK'ya bakın. Yaygın raster işlem kodlarının listesi `BitBlt` için Windows SDK'ya bakın.

*rektDest*<br/>
Hedefi tanımlayan `RECT` bir yapıya başvuru.

*noktaSrc*<br/>
Kaynak `POINT` dikdörtgenin sol üst köşesini gösteren bir yapı.

*pointMask*<br/>
Maske `POINT` bit haritasının sol üst köşesini gösteren bir yapı.

*pointDest*<br/>
Hedef dikdörtgenin `POINT` sol üst köşesini mantıksal birimler halinde tanımlayan bir yapıya başvuru.

### <a name="return-value"></a>Dönüş Değeri

Sıfır sız, başarılı ysa, aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem Windows NT, sürüm 4.0 ve daha sonra yalnızca için geçerlidir.

## <a name="cimageoperator-hbitmap"></a><a name="operator_hbitmap"></a>CImage::operatör HBITMAP

`CImage` Nesnenin ekli Windows GDI tutamacını almak için bu işleci kullanın. Bu işleç, bir HBITMAP nesnesinin doğrudan kullanımını destekleyen bir döküm operatörüdür.

## <a name="cimageplgblt"></a><a name="plgblt"></a>CImage::PlgBlt

Kaynak aygıt bağlamında dikdörtgenden hedef aygıt bağlamında paralelkenara bit blok aktarım gerçekleştirir.

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
Hedef aygıt bağlamına bir tanıtıcı.

*pPuanlar*<br/>
Hedef paralelkenarın üç köşesini tanımlayan mantıksal alanda üç noktalık bir diziiçin bir işaretçi. Kaynak dikdörtgenin sol üst köşesi bu dizideki ilk noktaya, sağ üst köşeye bu dizideki ikinci noktaya ve sol alt köşeye üçüncü noktaya eşlenir. Kaynak dikdörtgenin sağ alt köşesi paralelkenardaki örtük dördüncü noktaya eşlenir.

*hbmMaske*<br/>
Kaynak dikdörtgenin renklerini maskelemek için kullanılan isteğe bağlı tek renkli bit eşlemi için bir tutamaç.

*xSrc*<br/>
X-koordinat, mantıksal birimler, kaynak dikdörtgenin sol üst köşesinde.

*ySrc*<br/>
Y-koordinat, mantıksal birimler, kaynak dikdörtgenin sol üst köşesinde.

*nSrcGenişlik*<br/>
Kaynak dikdörtgenin mantıksal birimleriyle genişliği.

*nSrcYükseklik*<br/>
Mantıksal birimlerde, kaynak dikdörtgenin yüksekliği.

*xMaske*<br/>
Tek renkli bit haritasının sol üst köşesinin x-koordinatı.

*yMask*<br/>
Tek renkli bit haritasının sol üst köşesinin y-koordinatı.

*rectSrc*<br/>
Kaynak dikdörtgenin koordinatlarını belirten bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısına başvuru.

*pointMask*<br/>
Maske bit haritasının sol üst köşesini gösteren bir [POINT](/previous-versions/dd162805\(v=vs.85\)) yapısı.

### <a name="return-value"></a>Dönüş Değeri

Sıfır sız, başarılı ysa, aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*hbmMask* geçerli bir tek renkli `PlgBit` bit eşlemi tanımlıyorsa, kaynak dikdörtgenden renk veribitlerini maskelemek için bu bit eşlemi kullanır.

Bu yöntem Windows NT, sürüm 4.0 ve daha sonra yalnızca için geçerlidir. Daha ayrıntılı bilgi için Windows SDK'daki [PlgBlt'e](/windows/win32/api/wingdi/nf-wingdi-plgblt) bakın.

## <a name="cimagereleasedc"></a><a name="releasedc"></a>CImage::ReleaseDC

Aygıt bağlamını serbest bırakır.

```
void ReleaseDC() const throw();
```

### <a name="remarks"></a>Açıklamalar

Aynı anda aygıt bağlamına yalnızca bir bit eşlemesi seçilebildiği için, `ReleaseDC` [getdc'ye](#getdc)her çağrı için arama nız gerekir.

## <a name="cimagereleasegdiplus"></a><a name="releasegdiplus"></a>CImage::ReleaseGDIPlus

GDI+ tarafından kullanılan kaynakları salar.

```
void ReleaseGDIPlus() throw();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, genel `CImage` bir nesne tarafından ayrılan özgür kaynaklara çağrılmalıdır. Bkz. [CImage::CImage](#cimage).

## <a name="cimagesave"></a><a name="save"></a>CImage::Kaydet

Görüntüyü diskte belirtilen akışa veya dosyaya kaydeder.

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
Dosya görüntü verilerini içeren bir COM IStream nesnesine işaretçi.

*pszFileName*<br/>
Görüntü için dosya adı için bir işaretçi.

*guidFileType*<br/>
Görüntüyü kaydetmek için dosya türü. Aşağıdakilerden biri olabilir:

- `ImageFormatBMP`Sıkıştırılmamış bitmap görüntüsü.

- `ImageFormatPNG`Taşınabilir Ağ Grafiği (PNG) sıkıştırılmış görüntü.

- `ImageFormatJPEG`Bir JPEG sıkıştırılmış görüntü.

- `ImageFormatGIF`GIF sıkıştırılmış görüntü.

> [!NOTE]
> Sabitlerin tam listesi için Windows SDK'daki **Resim Dosyası Biçim Sabitleri'ne** bakın.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Belirtilen bir ad ve tür kullanarak görüntüyü kaydetmek için bu işlevi arayın. *GuidFileType* parametresi dahil edilmezse, görüntü biçimini belirlemek için dosya adının dosya uzantısı kullanılır. Uzantı sağlanmazsa, görüntü BMP biçiminde kaydedilir.

## <a name="cimagesetcolortable"></a><a name="setcolortable"></a>CImage::SetColorTable

DIB bölümünün paletindeki bir dizi giriş için kırmızı, yeşil, mavi (RGB) renk değerlerini ayarlar.

```
void SetColorTable(
    UINT iFirstColor,
    UINT nColors,
    const RGBQUAD* prgbColors) throw();
```

### <a name="parameters"></a>Parametreler

*iFirstColor*<br/>
Ayarlanan ilk girişin renk tablosu dizini.

*nColors*<br/>
Ayarlanan renk tablosu girişlerinin sayısı.

*prgbColors*<br/>
Renk tablosu girişlerini ayarlamak için [RGBQUAD](/windows/win32/api/wingdi/ns-wingdi-rgbquad) yapıları dizisini işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca DIB bölüm bit eşlemlerini destekler.

## <a name="cimagesetpixel"></a><a name="setpixel"></a>CImage::SetPixel

Bit haritasında belirli bir konumda bir pikselin rengini ayarlar.

```
void SetPixel(int x, int y, COLORREF color) throw();
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Ayarlanan pikselin yatay konumu.

*Y*<br/>
Ayarlanan pikselin dikey konumu.

*color*<br/>
Pikseli ayarladığınız renk.

### <a name="remarks"></a>Açıklamalar

Piksel koordinatları seçili kırpma bölgesinin dışında ysa, bu yöntem başarısız olur.

## <a name="cimagesetpixelindexed"></a><a name="setpixelindexed"></a>CImage::SetPixelIndexed

Piksel rengini renk paletinde *iIndex'te* bulunan renge ayarlar.

```
void SetPixelIndexed(int x, int y, int iIndex) throw();
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Ayarlanan pikselin yatay konumu.

*Y*<br/>
Ayarlanan pikselin dikey konumu.

*ıındex*<br/>
Renk paletindeki bir rengin dizini.

## <a name="cimagesetpixelrgb"></a><a name="setpixelrgb"></a>CImage::SetPixelRGB

Pikseli *x* ve *y* tarafından belirtilen konumlardaki *renkleri kırmızı,* yeşil, mavi (RGB) görüntüde r , *g*ve *b*ile gösterilen renklere ayarlar.

```
void SetPixelRGB(
    int x,
    int y,
    BYTE r,
    BYTE g,
    BYTE b) throw();
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Ayarlanan pikselin yatay konumu.

*Y*<br/>
Ayarlanan pikselin dikey konumu.

*R*<br/>
Kırmızı rengin yoğunluğu.

*G*<br/>
Yeşil rengin yoğunluğu.

*B*<br/>
Mavi rengin yoğunluğu.

### <a name="remarks"></a>Açıklamalar

Kırmızı, yeşil ve mavi parametrelerin her biri 0 ile 255 arasında bir sayıyla temsil edilir. Üç parametreyi de sıfıra ayarlarsanız, elde edilen renk siyahtır. Üç parametreyi de 255 olarak ayarlarsanız, elde edilen renk beyazdır.

## <a name="cimagesettransparentcolor"></a><a name="settransparentcolor"></a>CImage::SetTransparentColor

Belirli bir dizin ekinli konumda bir rengi saydam olarak ayarlar.

```
LONG SetTransparentColor(LONG iTransparentColor) throw();
```

### <a name="parameters"></a>Parametreler

*iTransparentColor*<br/>
Renk paletinde saydam olarak ayarlanan rengin dizin. -1 ise, hiçbir renk saydam olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Daha önce saydam olarak ayarlanmış renk dizini.

## <a name="cimagestretchblt"></a><a name="stretchblt"></a>CImage::StretchBlt

Kaynak aygıt bağlamından bu geçerli aygıt bağlamına bir bit eşlemi kopyalar.

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
Hedef aygıt bağlamına bir tanıtıcı.

*xDest*<br/>
X-koordinat, mantıksal birimler, hedef dikdörtgenin sol üst köşesinde.

*yDest*<br/>
Y-koordinat, mantıksal birimler, hedef dikdörtgenin sol üst köşesinde.

*nDestGenişliği*<br/>
Hedef dikdörtgenin mantıksal birimleriyle genişliği.

*nDestYükseklik*<br/>
Hedef dikdörtgenin mantıksal birimleriyle yüksekliği.

*dwROP*<br/>
Yapılacak raster operasyonu. Raster-işlem kodları, hedefi oluşturmak için kaynağın, hedefin ve desenin (şu anda seçili fırça tarafından tanımlandığı şekilde) bitlerinin tam olarak nasıl birleştirilecek olduğunu tanımlar. Diğer raster işlem kodlarının ve açıklamalarının listesi için Windows SDK'daki [BitBlt'e](/windows/win32/api/wingdi/nf-wingdi-bitblt) bakın.

*rektDest*<br/>
Hedefi tanımlayan bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısına başvuru.

*xSrc*<br/>
X-koordinat, mantıksal birimler, kaynak dikdörtgenin sol üst köşesinde.

*ySrc*<br/>
Y-koordinat, mantıksal birimler, kaynak dikdörtgenin sol üst köşesinde.

*nSrcGenişlik*<br/>
Kaynak dikdörtgenin mantıksal birimleriyle genişliği.

*nSrcYükseklik*<br/>
Mantıksal birimlerde, kaynak dikdörtgenin yüksekliği.

*rectSrc*<br/>
Kaynağı tanımlayan `RECT` bir yapıya başvuru.

### <a name="return-value"></a>Dönüş Değeri

Sıfır sız, başarılı ysa, aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK'daki [StretchBlt](/windows/win32/api/wingdi/nf-wingdi-stretchblt) bölümüne bakın.

## <a name="cimagetransparentblt"></a><a name="transparentblt"></a>CImage::TransparentBlt

Kaynak aygıt bağlamından bu geçerli aygıt bağlamına bir bit eşlemi kopyalar.

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
Hedef aygıt bağlamına bir tanıtıcı.

*xDest*<br/>
X-koordinat, mantıksal birimler, hedef dikdörtgenin sol üst köşesinde.

*yDest*<br/>
Y-koordinat, mantıksal birimler, hedef dikdörtgenin sol üst köşesinde.

*nDestGenişliği*<br/>
Hedef dikdörtgenin mantıksal birimleriyle genişliği.

*nDestYükseklik*<br/>
Hedef dikdörtgenin mantıksal birimleriyle yüksekliği.

*crŞeffaf*<br/>
Saydam olarak ele almak için kaynak bit haritasındaki renk. Varsayılan olarak, CLR_INVALID, şu anda görüntünün saydam renk olarak ayarlanmış renk kullanılması gerektiğini belirten.

*rektDest*<br/>
Hedefi tanımlayan bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısına başvuru.

*xSrc*<br/>
X-koordinat, mantıksal birimler, kaynak dikdörtgenin sol üst köşesinde.

*ySrc*<br/>
Y-koordinat, mantıksal birimler, kaynak dikdörtgenin sol üst köşesinde.

*nSrcGenişlik*<br/>
Kaynak dikdörtgenin mantıksal birimleriyle genişliği.

*nSrcYükseklik*<br/>
Mantıksal birimlerde, kaynak dikdörtgenin yüksekliği.

*rectSrc*<br/>
Kaynağı tanımlayan `RECT` bir yapıya başvuru.

### <a name="return-value"></a>Dönüş Değeri

DOĞRU eğer başarılı, aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

`TransparentBlt`piksel başına 4 bit ve piksel başına 8 bit kaynak bit eşlemleri için desteklenir. Saydamlıkla piksel başına 32 bit bit eşlemlerini belirtmek için [CImage::AlphaBlend'i](#alphablend) kullanın.

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

## <a name="see-also"></a>Ayrıca bkz.

[MMXSwarm Numunesi](../../overview/visual-cpp-samples.md)<br/>
[SimpleImage Örnek](../../overview/visual-cpp-samples.md)<br/>
[Aygıt-Bağımsız Biteşler](/windows/win32/gdi/device-independent-bitmaps)<br/>
[CreateDIBSection](/windows/win32/api/wingdi/nf-wingdi-createdibsection)<br/>
[ATL COM Masaüstü Bileşenleri](../../atl/atl-com-desktop-components.md)<br/>
[Aygıt-Bağımsız Biteşler](/windows/win32/gdi/device-independent-bitmaps)<br/>
[CreateDIBSection](/windows/win32/api/wingdi/nf-wingdi-createdibsection)
