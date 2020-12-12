---
description: 'Daha fazla bilgi edinin: CImage sınıfı'
title: CImage sınıfı
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
ms.openlocfilehash: a094aecfae57a678f306d00e0998247000361822
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166842"
---
# <a name="cimage-class"></a>CImage sınıfı

`CImage` JPEG, GIF, BMP ve Taşınabilir Ağ Grafikleri (PNG) biçimlerinde görüntü yükleme ve kaydetme özelliği de dahil olmak üzere gelişmiş bit eşlem desteği sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
class CImage
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CImage:: CImage](#cimage)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CImage:: harfler Blend](#alphablend)|Saydam veya yarı saydam piksel olan bit eşlemleri görüntüler.|
|[CImage:: Attach](#attach)|Nesnesine bir HBIT eşlem ekler `CImage` . , DIB olmayan bölüm bit eşlemler veya DIB bölümü bit eşlemleriyle kullanılabilir.|
|[CImage:: BitBlt](#bitblt)|Kaynak cihaz bağlamından bir bit eşlemi Bu geçerli cihaz bağlamına kopyalar.|
|[CImage:: Create](#create)|Bir DIB bölüm bit eşlemi oluşturur ve daha önce oluşturulmuş nesneye ekler `CImage` .|
|[CImage:: CreateEx](#createex)|Bir DIB bölümü bit eşlemi oluşturur (ek parametrelerle birlikte) ve daha önce oluşturulmuş nesneye iliştirir `CImage` .|
|[CImage::D estroy](#destroy)|Bit eşlemi `CImage` nesneden ayırır ve bit eşlemi yok eder.|
|[CImage::D etach](#detach)|Bir nesneden bit eşlemi ayırır `CImage` .|
|[CImage::D RAW](#draw)|Bir kaynak dikdörtgenden bir bit eşlemi hedef dikdörtgene kopyalar. `Draw` gerekirse, hedef dikdörtgenin boyutlarına uyacak şekilde bit eşlemi uzatır veya sıkıştırır ve Alfa karışım ve saydam renkleri işler.|
|[CImage:: GetBits](#getbits)|Bit eşlemin gerçek piksel değerlerine bir işaretçi alır.|
|[CImage:: GetBPP](#getbpp)|Piksel başına bitleri alır.|
|[CImage:: GetColorTable](#getcolortable)|Renk tablosundaki bir dizi girişi kırmızı, yeşil, mavi (RGB) renk değerleri alır.|
|[CImage:: GetDC](#getdc)|Geçerli bit eşlemin seçildiği cihaz bağlamını alır.|
|[CImage:: GetExporterFilterString](#getexporterfilterstring)|Kullanılabilir görüntü biçimlerini ve açıklamalarını bulur.|
|[CImage:: GetHeight](#getheight)|Geçerli görüntünün yüksekliğini piksel olarak alır.|
|[CImage:: Getımporterfilterstring](#getimporterfilterstring)|Kullanılabilir görüntü biçimlerini ve açıklamalarını bulur.|
|[CImage:: GetMaxColorTableEntries](#getmaxcolortableentries)|Renk tablosundaki en fazla girdi sayısını alır.|
|[CImage:: Getsıklık](#getpitch)|Geçerli görüntünün, bayt cinsinden perdesini alır.|
|[CImage:: GetPixel](#getpixel)|*X* ve *y* tarafından belirtilen pikselin rengini alır.|
|[CImage:: Getpikseleladdress](#getpixeladdress)|Belirli bir pikselin adresini alır.|
|[CImage:: GetTransparentColor](#gettransparentcolor)|Renk tablosundaki saydam rengin konumunu alır.|
|[CImage:: GetWidth](#getwidth)|Geçerli görüntünün genişliğini piksel olarak alır.|
|[CImage:: IsDibSection](#isdibsection)|Eklenen bit eşlemin bir DIB bölümü olup olmadığını belirler.|
|[CImage:: IsIndexed](#isindexed)|Bir bit eşlem renklerinin, dizinlenmiş bir paletle eşleştirildiğini gösterir.|
|[CImage:: IsNull](#isnull)|Kaynak bit eşlemin Şu anda yüklü olup olmadığını gösterir.|
|[CImage:: IsTransparencySupported](#istransparencysupported)|Uygulamanın saydam bit eşlemleri destekleyip desteklemediğini gösterir.|
|[CImage:: Load](#load)|Belirtilen dosyadan bir resim yükler.|
|[CImage:: LoadFromResource](#loadfromresource)|Belirtilen kaynaktan bir görüntü yükler.|
|[CImage:: MaskBlt](#maskblt)|Belirtilen maske ve raster işlemini kullanarak kaynak ve hedef bit eşlemlerin renk verilerini birleştirir.|
|[CImage::P lgBlt](#plgblt)|Kaynak cihaz bağlamındaki bir dikdörtgenden bir hedef cihaz bağlamında paralelkenar içine bir bit blok aktarımı gerçekleştirir.|
|[CImage:: ReleaseDC](#releasedc)|[CImage:: GetDC](#getdc)ile alınan cihaz bağlamını serbest bırakır.|
|[CImage:: ReleaseGDIPlus](#releasegdiplus)|GDI+ tarafından kullanılan kaynakları serbest bırakır. Genel bir nesne tarafından oluşturulan kaynakların serbest olması için çağrılmalıdır `CImage` .|
|[CImage:: Save](#save)|Bir görüntüyü belirtilen tür olarak kaydeder. `Save` görüntü seçenekleri belirtilemiyor.|
|[CImage:: SetColorTable](#setcolortable)|DIB bölümünün renk tablosundaki bir giriş aralığındaki kırmızı, yeşil, mavi RGB) renk değerlerini ayarlar.|
|[CImage:: SetPixel](#setpixel)|Belirtilen koordinatlardaki pikseli belirtilen renge ayarlar.|
|[CImage:: Setpixelındexed](#setpixelindexed)|Belirtilen koordinatlardaki pikseli, paletin belirtilen dizinindeki renge ayarlar.|
|[CImage:: SetPixelRGB](#setpixelrgb)|Belirtilen koordinatlardaki pikseli belirtilen kırmızı, yeşil, mavi (RGB) değere ayarlar.|
|[CImage:: SetTransparentColor](#settransparentcolor)|Rengin dizinini saydam olarak değerlendirilecek şekilde ayarlar. Paletteki yalnızca bir renk saydam olabilir.|
|[CImage:: uzatılabilir blt](#stretchblt)|Bir kaynak dikdörtgenden bir bit eşlemi, hedef dikdörtgenin boyutlarına uyacak şekilde genişleterek veya sıkıştırarak bir hedef dikdörtgene kopyalar.|
|[CImage:: TransparentBlt](#transparentblt)|Kaynak cihaz bağlamından bir bit eşlemi, bu geçerli cihaz bağlamına kopyalar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CImage:: operator HBıX](#operator_hbitmap)|Nesnesine eklenen Windows işleyicisini döndürür `CImage` .|

## <a name="remarks"></a>Açıklamalar

`CImage` cihazdan bağımsız bit eşlem (DIB) bölümleri olan bit eşlemler alır; Ancak [Create](#create) veya [CImage:: Load](#load) 'u yalnızca DIB bölümleri ile kullanabilirsiniz. Attach kullanarak bir nesneye DIB olmayan bölüm bit eşlemi ekleyebilirsiniz `CImage` , ancak bu [](#attach)durumda `CImage` yalnızca DIB bölümü bit eşlemlerini destekleyen aşağıdaki yöntemleri kullanamazsınız:

- [GetBits](#getbits)

- [GetColorTable](#getcolortable)

- [GetMaxColorTableEntries](#getmaxcolortableentries)

- [Getsıklık](#getpitch)

- [Getpikseleladdress](#getpixeladdress)

- [I' dizinli](#isindexed)

- [SetColorTable](#setcolortable)

Eklenen bir bit eşlemin bir DIB bölümü olup olmadığını anlamak için, [IsDibSection](#isdibsection)çağırın.

> [!NOTE]
> Visual Studio .NET 2003 ' de, bu sınıf oluşturulan nesne sayısının sayısını tutar `CImage` . Sayı 0 ' a her gittiğinde,, `GdiplusShutdown` GDI+ tarafından kullanılan kaynakları serbest bırakmak için otomatik olarak çağrılır. Bu sayede `CImage` , dll 'ler tarafından doğrudan veya dolaylı olarak oluşturulan tüm nesnelerin her zaman düzgün şekilde yok edileceği ve `GdiplusShutdown` öğesinden çağrılmamasını sağlar `DllMain` .

> [!NOTE]
> `CImage`BIR DLL içinde genel nesnelerin kullanılması önerilmez. `CImage`BIR DLL içinde genel bir nesne kullanmanız gerekiyorsa, GDI+ tarafından kullanılan kaynakları açıkça serbest bırakmak Için [CImage:: ReleaseGDIPlus](#releasegdiplus) ' ı çağırın.

`CImage` Yeni bir [CDC](../../mfc/reference/cdc-class.md)olarak seçilemez. `CImage` görüntü için kendi HDC 'sini oluşturur. Bir HBıX tek seferde yalnızca bir HDC 'de seçilebildiğinden, ile ilişkili HBIT eşlem `CImage` başka BIR HDC 'de seçilemez. CDC gerekiyorsa, ' dan HDC 'yi alın `CImage` ve bunu [CDC:: FromHandle](../../mfc/reference/cdc-class.md#fromhandle)' a verin.

## <a name="examples"></a>Örnekler

```cpp
// Get a CDC for the image
CDC* pDC = CDC::FromHandle(m_myImage.GetDC());

// Use pDC here
pDC->Rectangle(0, 40, 100, 50);
m_myImage.ReleaseDC();
```

`CImage`MFC projesinde kullandığınızda, projenizdeki üye Işlevleri [CBitmap](../../mfc/reference/cbitmap-class.md) nesnesine bir işaretçi beklediğini unutmayın. `CImage`Bu tür bir işlevle kullanmak istiyorsanız, [CMenu:: AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu)gibi, [CBitmap:: FromHandle](../../mfc/reference/cbitmap-class.md#fromhandle)kullanın, `CImage` hbımap inizi geçirin ve döndürülen öğesini kullanın `CBitmap*` .

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

Aracılığıyla `CImage` , BIR DIB 'nin gerçek bit bitlerini erişiminiz vardır. Bir `CImage` nesneyi, daha önce bir WIN32 HBIT veya DIB bölümünü kullandığınız her yerde kullanabilirsiniz.

`CImage`MFC veya ATL 'den kullanabilirsiniz.

> [!NOTE]
> Kullanarak bir proje oluşturduğunuzda `CImage` , `CString` *atlımage. h* dahil etmeden önce tanımlamanız gerekir. Projeniz MFC olmadan ATL kullanıyorsa, *atlımage. h* dahil etmeden önce *atlstr. h* ekleyin. Projeniz MFC kullanıyorsa (veya MFC desteği olan bir ATL projem ise), *atlımage. h* eklemeden önce *afxstr. h* 'yi dahil edin.
>
> Benzer şekilde, *atlımpl. cpp* dahil etmeden önce *atlımage. h* dahil etmeniz gerekir. Bunu kolayca başarmak için, *pch. h* 'Nize (Visual Studio 2017 ve önceki sürümlerde *stdadfx. h* ) *atlımage.* h ' yi ekleyin.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlımage. h

## <a name="cimagealphablend"></a><a name="alphablend"></a> CImage:: harfler Blend

Saydam veya yarı saydam piksel olan bit eşlemleri görüntüler.

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
Hedef cihaz bağlamının tanıtıcısı.

*xDest*<br/>
Hedef dikdörtgenin sol üst köşesinin, mantıksal birimlerde x koordinatı.

*En dest*<br/>
Hedef dikdörtgenin sol üst köşesinin, mantıksal birimlerde y koordinatı.

*bSrcAlpha*<br/>
Tüm kaynak bit eşlemde kullanılacak bir alfa saydamlığı değeri. Varsayılan 0xFF (255), resminizin donuk olduğunu ve yalnızca piksel başına Alfa değerlerini kullanmak istediğinizi varsayar.

*Barmerdop*<br/>
Kaynak ve hedef bit eşlemler için alfa karıştırma işlevi, kaynak bit eşlemin tamamına uygulanacak genel bir alfa değeri ve kaynak bit eşlemin biçim bilgileri. Kaynak ve hedef harmanlama işlevleri şu anda AC_SRC_OVER sınırlıdır.

*pointDest*<br/>
Mantıksal birimlerde hedef dikdörtgenin sol üst köşesini tanımlayan bir [nokta](/windows/win32/api/windef/ns-windef-point) yapısına başvuru.

*nDestWidth*<br/>
Hedef dikdörtgenin mantıksal birimlerindeki genişliği.

*nDestHeight*<br/>
Hedef dikdörtgenin mantıksal birimleri cinsinden yüksekliği.

*xSrc*<br/>
Kaynak dikdörtgenin sol üst köşesinin mantıksal x koordinatı.

*ySrc*<br/>
Kaynak dikdörtgenin sol üst köşesinin mantıksal y koordinatı.

*nSrcWidth*<br/>
Kaynak dikdörtgenin mantıksal birimlerindeki genişliği.

*nSrcHeight*<br/>
Kaynak dikdörtgenin mantıksal birimleri cinsinden yüksekliği.

*rectDest*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına bir başvuru, hedefi tanımlar.

*rectSrc*<br/>
`RECT`Kaynağı tanımlayarak bir yapıya başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Alfa Blend bit eşlemler piksel başına renk karıştırmasını destekler.

*BBlendOp* , AC_SRC_OVER varsayılana ayarlandığında kaynak bit eşlem, kaynak piksellerin Alfa değerlerine göre hedef bit eşlem üzerinden yerleştirilir.

## <a name="cimageattach"></a><a name="attach"></a> CImage:: Attach

Bir nesneye *Hbit eşlem* ekler `CImage` .

```cpp
void Attach(HBITMAP hBitmap, DIBOrientation eOrientation = DIBOR_DEFAULT) throw();
```

### <a name="parameters"></a>Parametreler

*HBITMAP*<br/>
Bir HBIT eşlem tanıtıcısı.

*Eyönlendirmede*<br/>
Bit eşlemin yönünü belirtir. Aşağıdakilerden biri olabilir:

- Bit eşlemin yönü DIBOR_DEFAULT işletim sistemi tarafından belirlenir.

- Bit eşlemin satırları DIBOR_BOTTOMUP ters sırada. Bu, [CImage:: GetBits](#getbits) 'in bit eşlem arabelleğinin sonuna yakın bir işaretçi döndürmesini sağlar ve [CImage:: getsıklık](#getpitch) negatif bir sayı döndürür.

- Bit eşlemin satırları DIBOR_TOPDOWN yukarıdan aşağıya doğru sırada. Bu, [CImage:: GetBits](#getbits) 'in bit eşlem arabelleğinin ilk baytına bir işaretçi döndürmesini sağlar ve [CImage:: getsıklık](#getpitch) pozitif bir sayı döndürür.

### <a name="remarks"></a>Açıklamalar

Bit eşlem, DIB olmayan bir bölüm bit eşlemi veya bir DIB bölümü bit eşlemi olabilir. Yalnızca DIB bölümü bit eşlemleriyle kullanabileceğiniz yöntemlerin listesi için [IsDibSection](#isdibsection) bölümüne bakın.

## <a name="cimagebitblt"></a><a name="bitblt"></a> CImage:: BitBlt

Kaynak cihaz bağlamından bir bit eşlemi Bu geçerli cihaz bağlamına kopyalar.

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
Hedef dikdörtgenin sol üst köşesinin mantıksal x koordinatı.

*En dest*<br/>
Hedef dikdörtgenin sol üst köşesinin mantıksal y koordinatı.

*dwROP*<br/>
Gerçekleştirilecek tarama işlemi. Raster-işlem kodları, hedefi oluşturmak için kaynak, hedef ve düzenin bitlerini (Şu anda seçili fırça tarafından tanımlanan şekilde) tam olarak nasıl birleştirileceğini tanımlar. Diğer raster işlem kodlarının listesi ve açıklamaları için Windows SDK [BitBlt](/windows/win32/api/wingdi/nf-wingdi-bitblt) ' i inceleyin.

*pointDest*<br/>
Hedef dikdörtgenin sol üst köşesini gösteren bir [nokta](/windows/win32/api/windef/ns-windef-point) yapısı.

*nDestWidth*<br/>
Hedef dikdörtgenin mantıksal birimlerindeki genişliği.

*nDestHeight*<br/>
Hedef dikdörtgenin mantıksal birimleri cinsinden yüksekliği.

*xSrc*<br/>
Kaynak dikdörtgenin sol üst köşesinin mantıksal x koordinatı.

*ySrc*<br/>
Kaynak dikdörtgenin sol üst köşesinin mantıksal y koordinatı.

*rectDest*<br/>
Hedef dikdörtgeni gösteren bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısı.

*pointSrc*<br/>
`POINT`Kaynak dikdörtgenin sol üst köşesini belirten bir yapı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi halde sıfır.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK [BitBlt](/windows/win32/api/wingdi/nf-wingdi-bitblt) bölümüne bakın.

## <a name="cimagecimage"></a><a name="cimage"></a> CImage:: CImage

Bir `CImage` nesnesi oluşturur.

```
CImage() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesneyi oluşturduktan sonra, nesnesine bir bit eşlem iliştirmek için [Create](#create), [Load](#load), [LoadFromResource](#loadfromresource)veya [Attach](#attach) komutunu çağırın.

**Göz önünde** Visual Studio 'da, bu sınıf oluşturulan nesne sayısının sayısını tutar `CImage` . Sayı 0 ' a her gittiğinde,, `GdiplusShutdown` GDI+ tarafından kullanılan kaynakları serbest bırakmak için otomatik olarak çağrılır. Böylece `CImage` , dll 'ler tarafından doğrudan veya dolaylı olarak oluşturulan tüm nesnelerin her zaman düzgün şekilde yok edileceği ve `GdiplusShutdown` DllMain 'den çağrılmamasını sağlar.

`CImage`BIR DLL içinde genel nesnelerin kullanılması önerilmez. `CImage`BIR DLL içinde genel bir nesne kullanmanız gerekiyorsa, GDI+ tarafından kullanılan kaynakları açıkça serbest bırakmak Için [CImage:: ReleaseGDIPlus](#releasegdiplus) ' ı çağırın.

## <a name="cimagecreate"></a><a name="create"></a> CImage:: Create

Bir `CImage` bit eşlem oluşturur ve önceden oluşturulmuş `CImage` nesneye ekler.

```
BOOL Create(
    int nWidth,
    int nHeight,
    int nBPP,
    DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Parametreler

*nWidth*<br/>
`CImage`Bit eşlemin piksel cinsinden genişliği.

*nHeight*<br/>
`CImage`Bit eşlemin piksel cinsinden yüksekliği. *NHeight* değeri pozitifse, bit eşlem BIR alt DIB olur ve bu, sol alt köşenin kökenidir. *NHeight* değeri negatifse, bit eşlem bir üst-aşağı DIB olur ve kaynak sol üst köşesindedir.

*nBPP*<br/>
Bit eşlemdeki piksel başına bit sayısı. Genellikle 4, 8, 16, 24 veya 32. Tek renkli bit eşlemler veya maskeler için 1 olabilir.

*dwFlags*<br/>
Bit eşlem nesnesinin bir alfa kanalına sahip olup olmadığını belirtir. Aşağıdaki değerlerden oluşan sıfır veya daha fazla değerden oluşan bir bileşim olabilir:

- *Createharflerden kanal* Yalnızca *nBPP* 32 Ise ve *eCompression* BI_RGB kullanılabilir. Belirtilmişse, oluşturulan görüntüde her piksel için bir Alfa (saydamlık) değeri bulunur ve her bir pikselin 4 baytında (Alfa 32 bit olmayan bir görüntüde kullanılmıyor) depolanır. Bu alfa kanalı, [CImage:: harflerden Blend](#alphablend)çağrılırken otomatik olarak kullanılır.

> [!NOTE]
> [CImage::D RAW](#draw)çağrılarında, alfa kanalına sahip görüntüler otomatik olarak hedefe karışalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

## <a name="cimagecreateex"></a><a name="createex"></a> CImage:: CreateEx

Bir `CImage` bit eşlem oluşturur ve önceden oluşturulmuş `CImage` nesneye ekler.

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
`CImage`Bit eşlemin piksel cinsinden genişliği.

*nHeight*<br/>
`CImage`Bit eşlemin piksel cinsinden yüksekliği. *NHeight* değeri pozitifse, bit eşlem BIR alt DIB olur ve bu, sol alt köşenin kökenidir. *NHeight* değeri negatifse, bit eşlem bir üst-aşağı DIB olur ve kaynak sol üst köşesindedir.

*nBPP*<br/>
Bit eşlemdeki piksel başına bit sayısı. Genellikle 4, 8, 16, 24 veya 32. Tek renkli bit eşlemler veya maskeler için 1 olabilir.

*eCompression*<br/>
Sıkıştırılmış bir alt bit eşlem için sıkıştırmanın türünü belirtir (yukarıdan aşağıya doğru sıkıştırma yapılamaz). Aşağıdaki değerlerden biri olabilir:

- Biçimin sıkıştırması BI_RGB. Çağrılırken bu değerin belirtilmesi `CImage::CreateEx` , çağırma ile eşdeğerdir `CImage::Create` .

- BI_BITFIELDS biçim sıkıştırılmamış ve renk tablosu, her bir pikselin sırasıyla kırmızı, yeşil ve mavi bileşenleri belirten üç DWORD renk maskelerinden oluşur. Bu, 16 ve 32-BPP bit eşlemleriyle kullanıldığında geçerlidir.

*pdwBitfields*<br/>
Yalnızca *eCompression* BI_BITFIELDS olarak ayarlandıysa kullanılır, aksı takdirde null olmalıdır. Her bir pikselin, rengin kırmızı, yeşil ve mavi bileşenleri için hangi bitlerin kullanılacağını belirten, üç DWORD bit maskesi dizisine yönelik bir işaretçi. Bitfields kısıtlamaları hakkında daha fazla bilgi için Windows SDK içindeki [Bitmapınfoheader](/windows/win32/api/wingdi/ns-wingdi-bitmapinfoheader) bölümüne bakın.

*dwFlags*<br/>
Bit eşlem nesnesinin bir alfa kanalına sahip olup olmadığını belirtir. Aşağıdaki değerlerden oluşan sıfır veya daha fazla değerden oluşan bir bileşim olabilir:

- *Createharflerden kanal* Yalnızca *nBPP* 32 Ise ve *eCompression* BI_RGB kullanılabilir. Belirtilmişse, oluşturulan görüntüde her piksel için bir Alfa (saydamlık) değeri bulunur ve her bir pikselin 4 baytında (Alfa 32 bit olmayan bir görüntüde kullanılmıyor) depolanır. Bu alfa kanalı, [CImage:: harflerden Blend](#alphablend)çağrılırken otomatik olarak kullanılır.

   > [!NOTE]
   > [CImage::D RAW](#draw)çağrılarında, alfa kanalına sahip görüntüler otomatik olarak hedefe karışalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa doğru. Aksi halde yanlış.

### <a name="example"></a>Örnek

Aşağıdaki örnek, her pikseli kodlamak için 16 bit kullanan bir 100x100 piksel bit eşlem oluşturur. Belirli bir 16 bit pikselde, BITS 0-3 kırmızı bileşeni kodlayıp, BITS 4-7 olarak yeşil ve BITS 8-11 kodlama mavi. Kalan 4 bit kullanılmıyor.

```cpp
DWORD adwBitmasks[3] = { 0x0000000f, 0x000000f0, 0x00000f00 };
m_myImage.CreateEx(100, 100, 16, BI_BITFIELDS, adwBitmasks, 0);
```

## <a name="cimagedestroy"></a><a name="destroy"></a> CImage::D estroy

Bit eşlemi `CImage` nesneden ayırır ve bit eşlemi yok eder.

```cpp
void Destroy() throw();
```

## <a name="cimagedetach"></a><a name="detach"></a> CImage::D etach

Bir nesneden bir bit eşlemi ayırır `CImage` .

```
HBITMAP Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bit eşlem için bir tanıtıcı ayrılır veya hiçbir bit eşlem iliştirilmişse NULL olur.

## <a name="cimagedraw"></a><a name="draw"></a> CImage::D RAW

Kaynak cihaz bağlamından bir bit eşlemi geçerli cihaz bağlamına kopyalar.

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
Hedef cihaz bağlamına yönelik bir tanıtıcı.

*xDest*<br/>
Hedef dikdörtgenin sol üst köşesinin, mantıksal birimlerde x koordinatı.

*En dest*<br/>
Hedef dikdörtgenin sol üst köşesinin, mantıksal birimlerde y koordinatı.

*nDestWidth*<br/>
Hedef dikdörtgenin mantıksal birimlerindeki genişliği.

*nDestHeight*<br/>
Hedef dikdörtgenin mantıksal birimleri cinsinden yüksekliği.

*xSrc*<br/>
Kaynak dikdörtgenin sol üst köşesinin, mantıksal birimlerde x koordinatı.

*ySrc*<br/>
Kaynak dikdörtgenin sol üst köşesinin, mantıksal birimlerde y koordinatı.

*nSrcWidth*<br/>
Kaynak dikdörtgenin mantıksal birimlerindeki genişliği.

*nSrcHeight*<br/>
Kaynak dikdörtgenin mantıksal birimleri cinsinden yüksekliği.

*rectDest*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına bir başvuru, hedefi tanımlar.

*rectSrc*<br/>
`RECT`Kaynağı tanımlayarak bir yapıya başvuru.

*pointDest*<br/>
Mantıksal birimlerde hedef dikdörtgenin sol üst köşesini tanımlayan bir [nokta](/windows/win32/api/windef/ns-windef-point) yapısına başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`Draw` görüntüde saydam bir renk veya alfa kanalı [yoksa, aynı işlemi, aynı](#stretchblt)işlemi Bu durumda, `Draw` gereken [TransparentBlt](#transparentblt) veya [harflerden Blend](#alphablend) ile aynı işlemi gerçekleştirir.

`Draw`Kaynak dikdörtgeni belirtmeyen sürümleri için, kaynak görüntünün tamamı varsayılandır. `Draw`Hedef dikdörtgen için bir boyut belirtmeyen sürümü için, kaynak görüntünün boyutu varsayılandır ve bir uzatma ya da küçültme gerçekleşmez.

## <a name="cimagegetbits"></a><a name="getbits"></a> CImage:: GetBits

Bit eşlemdeki belirli bir pikselin gerçek bit değerlerine yönelik bir işaretçi alır.

```cpp
void* GetBits() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bit eşlem arabelleği işaretçisi. Bit eşlem, aşağıdan yukarıya bir DIB ise, işaretçi arabelleğin sonuna yakın bir işaret eder. Bit eşlem bir yukarıdan aşağı DIB ise, işaretçi arabelleğin ilk baytını işaret eder.

### <a name="remarks"></a>Açıklamalar

Bu işaretçiyi, [Getsıklık](#getpitch)tarafından döndürülen değerle birlikte kullanarak bir görüntüdeki tek tek pikselleri bulabilir ve değiştirebilirsiniz.

> [!NOTE]
> Bu yöntem yalnızca DIB bölümü bit eşlemlerini destekler; Sonuç olarak, bir `CImage` nesnenin piksellere BIR DIB bölümünün pikselleriyle aynı şekilde erişirsiniz. Döndürülen işaretçi, (0, 0) konumundaki pikseli işaret eder.

## <a name="cimagegetbpp"></a><a name="getbpp"></a> CImage:: GetBPP

Piksel başına bit değerini alır.

```
int GetBPP() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Piksel başına bit sayısı.

### <a name="remarks"></a>Açıklamalar

Bu değer, bit eşlemdeki en fazla renk sayısını ve her pikseli tanımlayan bitlerin sayısını belirler.

Piksel başına bit sayısı genellikle 1, 4, 8, 16, 24 veya 32 ' dir. `biBitCount`Bu değer hakkında daha fazla bilgi için Windows SDK [Bitmapınfoheader](/windows/win32/api/wingdi/ns-wingdi-bitmapinfoheader) üyesine bakın.

## <a name="cimagegetcolortable"></a><a name="getcolortable"></a> CImage:: GetColorTable

DIB bölümünün paletindeki bir giriş aralığından kırmızı, yeşil, mavi (RGB) renk değerleri alır.

```cpp
void GetColorTable(
    UINT iFirstColor,
    UINT nColors,
    RGBQUAD* prgbColors) const throw();
```

### <a name="parameters"></a>Parametreler

*ıfırstcolor*<br/>
Alınacak ilk girdinin renk tablosu dizini.

*Nrenkler*<br/>
Alınacak renk tablosu girdilerinin sayısı.

*Prgbrenkler*<br/>
Renk tablosu girdilerini almak için [Rgbdörtlü](/windows/win32/api/wingdi/ns-wingdi-rgbquad) yapıların dizisine yönelik bir işaretçi.

## <a name="cimagegetdc"></a><a name="getdc"></a> CImage:: GetDC

Şu anda seçili olan görüntünün bulunduğu cihaz bağlamını alır.

```
HDC GetDC() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Cihaz bağlamına yönelik bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Her çağrısı için `GetDC` , [ReleaseDC](#releasedc)'ye yönelik sonraki bir çağrın olması gerekir.

## <a name="cimagegetexporterfilterstring"></a><a name="getexporterfilterstring"></a> CImage:: GetExporterFilterString

Görüntüleri kaydetmek için kullanılabilecek görüntü biçimlerini bulur.

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
Bir `CSimpleString` nesneye başvuru. Daha fazla bilgi için bkz. **açıklamalar** .

*aguidFileTypes*<br/>
Her öğesi dizedeki dosya türlerinden birine karşılık gelen bir GUID dizisi. *PszAllFilesDescription* örneğinde aşağıdaki örnekte, *aguidFileTypes*[0] GUID_NULL ve kalan dizi değerleri geçerli işletim sistemi tarafından desteklenen görüntü dosyası biçimleridir.

> [!NOTE]
> Sabitlerin tamamen listesi için, bkz. Windows SDK **görüntü dosyası biçimi sabitleri** .

*Pszallfilesaçıklaması*<br/>
Bu parametre NULL değilse, filtre dizesinde listenin başlangıcında bir ek filtre olacaktır. Bu filtre, açıklaması için *pszAllFilesDescription* öğesinin geçerli değerine sahip olur ve listedeki diğer herhangi bir dışarı aktarma tarafından desteklenen herhangi bir uzantının dosyalarını kabul eder.

Örneğin:

```cpp
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any exporter.
CImage::GetExporterFilterString(
    strExporters, aguidFileTypes,
_T("All Image Files"));
```

*dwExclude*<br/>
Listeden dışlanacak dosya türlerini belirten bit bayrakları kümesi. İzin verilen bayraklar şunlardır:

- `excludeGIF` = 0x01, GIF dosyalarını dışlar.

- `excludeBMP` = 0x02, BMP (Windows bit eşlem) dosyalarını dışlar.

- `excludeEMF` = 0x04, EMF (Gelişmiş Meta dosyası) dosyalarını dışlar.

- `excludeWMF` = 0x08 WMF (Windows meta dosyası) dosyalarını dışlar.

- `excludeJPEG` = 0x10 JPEG dosyalarını dışlar.

- `excludePNG` = 0x20 PNG dosyalarını dışlar.

- `excludeTIFF` = 0x40 TIFF dosyalarını dışlar.

- `excludeIcon` = 0x80 ICO (Windows simge) dosyalarını dışlar.

- `excludeOther` = 0x80000000 Yukarıda listelenmeyen diğer dosya türlerini dışlar.

- `excludeDefaultLoad` = 0 yükleme için tüm dosya türleri varsayılan olarak dahil edilir

- `excludeDefaultSave` = `excludeIcon &#124; excludeEMF &#124; excludeWMF` Kaydetmek için, bu dosyalar genellikle özel gereksinimlere sahip oldukları için varsayılan olarak dışlanır.

*chSeparator*<br/>
Resim biçimleri arasında kullanılan ayırıcı. Daha fazla bilgi için bkz. **açıklamalar** .

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Dosya farklı Kaydet iletişim kutusunda kullanılabilir görüntü biçimlerinin dosya uzantılarını ortaya çıkarmak için, sonuçta elde edilen biçim dizesini MFC [CFileDialog](../../mfc/reference/cfiledialog-class.md) nesnesine geçirebilirsiniz.

*StrExporter* parametresi şu biçimdedir:

dosya description0&#124;\* . ext0&#124;filedescription1&#124;\* . EXT1&#124;... Dosya Açıklaması *n*&#124;\* . ext *n*&#124;&#124;

Burada ' &#124; ' tarafından belirtilen ayırıcı karakterdir `chSeparator` . Örneğin:

`"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`

Bu dizeyi bir MFC nesnesine geçirirseniz, ' &#124; ' varsayılan ayırıcısını kullanın `CFileDialog` . Bu dizeyi ortak bir dosya Kaydet iletişim kutusuna geçirirseniz ' \ 0 ' null ayırıcısını kullanın.

## <a name="cimagegetheight"></a><a name="getheight"></a> CImage:: GetHeight

Resmin piksel cinsinden yüksekliğini alır.

```
int GetHeight() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Resmin piksel cinsinden yüksekliği.

## <a name="cimagegetimporterfilterstring"></a><a name="getimporterfilterstring"></a> CImage:: Getımporterfilterstring

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

*Önemli bir çaba*<br/>
Bir `CSimpleString` nesneye başvuru. Daha fazla bilgi için bkz. **açıklamalar** .

*aguidFileTypes*<br/>
Her öğesi dizedeki dosya türlerinden birine karşılık gelen bir GUID dizisi. *PszAllFilesDescription* örneğinde aşağıdaki örnekte, *aguidFileTypes*[0], kalan dizi değerleriyle birlikte GUID_NULL, geçerli işletim sistemi tarafından desteklenen görüntü dosyası biçimleridir.

> [!NOTE]
> Sabitlerin tamamen listesi için, bkz. Windows SDK **görüntü dosyası biçimi sabitleri** .

*Pszallfilesaçıklaması*<br/>
Bu parametre NULL değilse, filtre dizesinde listenin başlangıcında bir ek filtre olacaktır. Bu filtre, açıklaması için *pszAllFilesDescription* öğesinin geçerli değerine sahip olur ve listedeki diğer herhangi bir dışarı aktarma tarafından desteklenen herhangi bir uzantının dosyalarını kabul eder.

Örneğin:

```cpp
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any importer.
CImage::GetImporterFilterString(
    strImporters, aguidFileTypes,
_T("All Image Files"));
```

*dwExclude*<br/>
Listeden dışlanacak dosya türlerini belirten bit bayrakları kümesi. İzin verilen bayraklar şunlardır:

- `excludeGIF` = 0x01, GIF dosyalarını dışlar.

- `excludeBMP` = 0x02, BMP (Windows bit eşlem) dosyalarını dışlar.

- `excludeEMF` = 0x04, EMF (Gelişmiş Meta dosyası) dosyalarını dışlar.

- `excludeWMF` = 0x08 WMF (Windows meta dosyası) dosyalarını dışlar.

- `excludeJPEG` = 0x10 JPEG dosyalarını dışlar.

- `excludePNG` = 0x20 PNG dosyalarını dışlar.

- `excludeTIFF` = 0x40 TIFF dosyalarını dışlar.

- `excludeIcon` = 0x80 ICO (Windows simge) dosyalarını dışlar.

- `excludeOther` = 0x80000000 Yukarıda listelenmeyen diğer dosya türlerini dışlar.

- `excludeDefaultLoad` = 0 yükleme için tüm dosya türleri varsayılan olarak dahil edilir

- `excludeDefaultSave` = `excludeIcon &#124; excludeEMF &#124; excludeWMF` Kaydetmek için, bu dosyalar genellikle özel gereksinimlere sahip oldukları için varsayılan olarak dışlanır.

*chSeparator*<br/>
Resim biçimleri arasında kullanılan ayırıcı. Daha fazla bilgi için bkz. **açıklamalar** .

### <a name="remarks"></a>Açıklamalar

**Dosya Aç** iletişim kutusunda kullanılabilir görüntü biçimlerinin dosya uzantılarını göstermek için, sonuçta elde edilen BIÇIM dizesini MFC [CFileDialog](../../mfc/reference/cfiledialog-class.md) nesnesine geçirebilirsiniz.

Bu parametre *Şu* biçimdedir:

dosya description0&#124;\* . ext0&#124;filedescription1&#124;\* . EXT1&#124;... Dosya Açıklaması *n*&#124;\* . ext *n*&#124;&#124;

Burada ' &#124; ', *chSeparator* tarafından belirtilen ayırıcı karakterdir. Örneğin:

`"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`

Bu dizeyi bir MFC nesnesine geçirirseniz, ' &#124; ' varsayılan ayırıcısını kullanın `CFileDialog` . Bu dizeyi ortak bir **Dosya Aç** iletişim kutusuna geçirirseniz ' \ 0 ' null ayırıcısını kullanın.

## <a name="cimagegetmaxcolortableentries"></a><a name="getmaxcolortableentries"></a> CImage:: GetMaxColorTableEntries

Renk tablosundaki en fazla girdi sayısını alır.

```
int GetMaxColorTableEntries() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Renk tablosundaki girdi sayısı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca DIB bölümü bit eşlemlerini destekler.

## <a name="cimagegetpitch"></a><a name="getpitch"></a> CImage:: Getsıklık

Bir görüntünün perdesini alır.

```
int GetPitch() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Görüntünün sıklığı. Dönüş değeri negatifse, bit eşlem bir alt DIB ve kaynak sol alt köşenin kaynağı olur. Dönüş değeri pozitif ise, bit eşlem bir üst-aşağı DIB olur ve kaynak sol üst köşesindedir.

### <a name="remarks"></a>Açıklamalar

Sıklık, bir bit eşlem çizgisinin başlangıcını ve sonraki bit eşlem çizgisinin başlangıcını temsil eden iki bellek adresi arasındaki uzaklığın bayt cinsinden uzaklığı. Sıklık bayt cinsinden ölçüldüğü için bir görüntünün sıklığı piksel biçimini belirlemenize yardımcı olur. Sıklık, bit eşlem için ayrılan ek belleği da içerebilir.

`GetPitch`Bir görüntünün tek tek piksellerini bulmak Için [GetBits](#getbits) ile kullanın.

> [!NOTE]
> Bu yöntem yalnızca DIB bölümü bit eşlemlerini destekler.

## <a name="cimagegetpixel"></a><a name="getpixel"></a> CImage:: GetPixel

*X* ve *y* tarafından belirtilen konumdaki pikselin rengini alır.

```
COLORREF GetPixel(int x, int y) const throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Pikselin x koordinatı.

*Iz*<br/>
Pikselin y koordinatı.

### <a name="return-value"></a>Dönüş Değeri

Pikselin kırmızı, yeşil, mavi (RGB) değeri. Piksel geçerli kırpma bölgesinin dışındaysa, dönüş değeri CLR_INVALID.

## <a name="cimagegetpixeladdress"></a><a name="getpixeladdress"></a> CImage:: Getpikseleladdress

Bir pikselin tam adresini alır.

```cpp
void* GetPixelAddress(int x, int y) throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Pikselin x koordinatı.

*Iz*<br/>
Pikselin y koordinatı.

### <a name="remarks"></a>Açıklamalar

Adres bir pikselin koordinatlarına, bit eşlemin sıklığa ve piksel başına bitlere göre belirlenir.

Piksel başına 8 bitten az olan biçimler için, bu yöntem, pikseli içeren baytın adresini döndürür. Örneğin, resim biçiminizdeki piksel başına 4 bit varsa, `GetPixelAddress` bayttaki ilk pikselin adresini döndürür ve bayt başına 2 piksel hesaplamalısınız.

> [!NOTE]
> Bu yöntem yalnızca DIB bölümü bit eşlemlerini destekler.

## <a name="cimagegettransparentcolor"></a><a name="gettransparentcolor"></a> CImage:: GetTransparentColor

Renk paletindeki saydam rengin dizinli konumunu alır.

```
LONG GetTransparentColor() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Saydam rengin dizini.

## <a name="cimagegetwidth"></a><a name="getwidth"></a> CImage:: GetWidth

Resmin piksel cinsinden genişliğini alır.

```
int GetWidth() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bit eşlemin piksel cinsinden genişliği.

## <a name="cimageisdibsection"></a><a name="isdibsection"></a> CImage:: IsDibSection

Eklenen bit eşlemin bir DIB bölümü olup olmadığını belirler.

```
bool IsDIBSection() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ekli bit eşlem bir DIB bölümse, doğru. Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bit eşlem bir DIB bölümü değilse, `CImage` yalnızca DIB bölümü bit eşlemlerini destekleyen aşağıdaki yöntemleri kullanamazsınız:

- [GetBits](#getbits)

- [GetColorTable](#getcolortable)

- [GetMaxColorTableEntries](#getmaxcolortableentries)

- [Getsıklık](#getpitch)

- [Getpikseleladdress](#getpixeladdress)

- [I' dizinli](#isindexed)

- [SetColorTable](#setcolortable)

## <a name="cimageisindexed"></a><a name="isindexed"></a> CImage:: IsIndexed

Bit eşlemin piksel bir renk paletine eşlenip eşlenmeyeceğini belirler.

```
bool IsIndexed() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dizine alınmışsa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, yalnızca bit eşlem 8 bit (256 renk) veya daha az olduğunda TRUE döndürür.

> [!NOTE]
> Bu yöntem yalnızca DIB bölümü bit eşlemlerini destekler.

## <a name="cimageisnull"></a><a name="isnull"></a> CImage:: IsNull

Bir bit eşlemin Şu anda yüklü olup olmadığını belirler.

```
bool IsNull() const throw();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir bit eşlem Şu anda yüklü değilse TRUE değerini döndürür; Aksi halde yanlış.

## <a name="cimageistransparencysupported"></a><a name="istransparencysupported"></a> CImage:: IsTransparencySupported

Uygulamanın saydam bit eşlemleri destekleyip desteklemediğini gösterir.

```
static BOOL IsTransparencySupported() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli platform saydamlığı destekliyorsa sıfır dışı. Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri sıfır değilse ve saydamlık destekleniyorsa, bir [Alfablend](#alphablend), [TransparentBlt](#transparentblt)veya [Draw](#draw) çağrısı saydam renkleri işleymeyecektir.

## <a name="cimageload"></a><a name="load"></a> CImage:: Load

Bir görüntü yükler.

```
HRESULT Load(LPCTSTR pszFileName) throw();
HRESULT Load(IStream* pStream) throw();
```

### <a name="parameters"></a>Parametreler

*pszFileName*<br/>
Yüklenecek görüntü dosyasının adını içeren bir dize işaretçisi.

*pStream*<br/>
Yüklenecek görüntü dosyasının adını içeren akışa yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

*PszFileName* veya *pStream* tarafından belirtilen görüntüyü yükler.

Geçerli görüntü türleri BMP, GIF, JPEG, PNG ve TIFF ' dir.

## <a name="cimageloadfromresource"></a><a name="loadfromresource"></a> CImage:: LoadFromResource

Bir BITMAP kaynağından bir görüntü yükler.

```cpp
void LoadFromResource(
    HINSTANCE hInstance,
    LPCTSTR pszResourceName) throw();

void LoadFromResource(
    HINSTANCE hInstance,
    UINT nIDResource) throw();
```

### <a name="parameters"></a>Parametreler

*HINSTANCE*<br/>
Yüklenecek görüntüyü içeren modülün bir örneğine yönelik işleyici.

*pszResourceName*<br/>
Yüklenecek görüntüyü içeren kaynağın adını içeren dizeye yönelik bir işaretçi.

*nIDResource*<br/>
Yüklenecek kaynağın KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Kaynak BIT eşlem türünde olmalıdır.

## <a name="cimagemaskblt"></a><a name="maskblt"></a> CImage:: MaskBlt

Belirtilen maske ve raster işlemini kullanarak kaynak ve hedef bit eşlemlerin renk verilerini birleştirir.

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
Yürütülebiliri kaynağı içeren modülün tanıtıcısı.

*xDest*<br/>
Hedef dikdörtgenin sol üst köşesinin, mantıksal birimlerde x koordinatı.

*En dest*<br/>
Hedef dikdörtgenin sol üst köşesinin, mantıksal birimlerde y koordinatı.

*nDestWidth*<br/>
Hedef dikdörtgenin ve kaynak bit eşlemin mantıksal birimlerde Genişlik.

*nDestHeight*<br/>
Hedef dikdörtgenin ve kaynak bit eşlemin mantıksal birimlerde yükseklik.

*xSrc*<br/>
Kaynak bit eşlemin sol üst köşesinin mantıksal x koordinatı.

*ySrc*<br/>
Kaynak bit eşlemin sol üst köşesinin mantıksal y koordinatı.

*hbmMask*<br/>
Kaynak cihaz bağlamındaki renk bit eşlemiyle birlikte bulunan tek renkli maske bit eşlemi işleme.

*xMask*<br/>
*HbmMask* parametresi tarafından belirtilen maske bit eşlemi için yatay piksel boşluğu.

*Yımask*<br/>
*HbmMask* parametresi tarafından belirtilen maske bit eşlemi için dikey piksel boşluğu.

*dwROP*<br/>
Yöntemin kaynak ve hedef verilerin birleşimini denetlemek için kullandığı ön plan ve arka plan Üçlü tarama işlem kodlarını belirtir. Arka plan tarama işlem kodu, bu değerin yüksek sıralı sözcüğünün üst sıra baytında depolanır; ön plan tarama işlem kodu, bu değerin üst-sıra sözcüğünün alt sıra baytında depolanır; Bu değerin düşük sıralı sözcüğü yok sayılır ve sıfır olmalıdır. Bu yöntemin bağlamındaki ön plan ve arka plan hakkında bir tartışma için `MaskBlt` Windows SDK bakın. Ortak tarama işlemi kodlarının listesi için `BitBlt` Windows SDK bakın.

*rectDest*<br/>
`RECT`Hedefi tanımlayan bir yapıya başvuru.

*pointSrc*<br/>
`POINT`Kaynak dikdörtgenin sol üst köşesini belirten bir yapı.

*pointMask*<br/>
`POINT`Maske bit eşlemin sol üst köşesine işaret eden bir yapı.

*pointDest*<br/>
`POINT`Mantıksal birimlerde hedef dikdörtgenin sol üst köşesini tanımlayan bir yapıya başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca Windows NT, sürüm 4,0 ve üzeri için geçerlidir.

## <a name="cimageoperator-hbitmap"></a><a name="operator_hbitmap"></a> CImage:: operator HBıX

Nesnenin ekli Windows GDI işleyicisini almak için bu işleci kullanın `CImage` . Bu işleç, bir HBITMAP nesnesinin doğrudan kullanımını destekleyen bir atama işleçtir.

## <a name="cimageplgblt"></a><a name="plgblt"></a> CImage::P lgBlt

Kaynak cihaz bağlamındaki bir dikdörtgenden bir hedef cihaz bağlamında paralelkenar içine bir bit blok aktarımı gerçekleştirir.

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
Hedef cihaz bağlamına yönelik bir tanıtıcı.

*Pnoktaları*<br/>
Mantıksal alandaki, hedef paralel kenarın üç köşesini tanımlayan üç nokta dizisine yönelik bir işaretçi. Kaynak dikdörtgenin sol üst köşesi, bu dizideki ilk noktaya, sağ üst köşenin bu dizideki ikinci noktaya ve üçüncü noktanın sol alt köşesine eşlenir. Kaynak dikdörtgenin sağ alt köşesi paralelkenar içindeki örtük dördüncü noktaya eşlenir.

*hbmMask*<br/>
Kaynak dikdörtgenin renklerini maskelemek için kullanılan isteğe bağlı bir tek renkli bit eşlem tutamacı.

*xSrc*<br/>
Kaynak dikdörtgenin sol üst köşesinin, mantıksal birimlerde x koordinatı.

*ySrc*<br/>
Kaynak dikdörtgenin sol üst köşesinin, mantıksal birimlerde y koordinatı.

*nSrcWidth*<br/>
Kaynak dikdörtgenin mantıksal birimlerindeki genişliği.

*nSrcHeight*<br/>
Kaynak dikdörtgenin mantıksal birimleri cinsinden yüksekliği.

*xMask*<br/>
Tek renkli bit eşlemin sol üst köşesinin x koordinatı.

*Yımask*<br/>
Tek renkli bit eşlemin sol üst köşesinin y koordinatı.

*rectSrc*<br/>
Kaynak dikdörtgenin koordinatlarını belirten bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına başvuru.

*pointMask*<br/>
Maske bit eşlemin sol üst köşesine Işaret eden bir [nokta](/windows/win32/api/windef/ns-windef-point) yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

*HbmMask* geçerli bir tek renkli bit eşlem tanımlarsa, `PlgBit` kaynak dikdörtgenden renk verileri bitlerini maskelemek için bu bit eşlemi kullanır.

Bu yöntem yalnızca Windows NT, sürüm 4,0 ve üzeri için geçerlidir. Daha ayrıntılı bilgi için Windows SDK [PlgBlt](/windows/win32/api/wingdi/nf-wingdi-plgblt) bölümüne bakın.

## <a name="cimagereleasedc"></a><a name="releasedc"></a> CImage:: ReleaseDC

Cihaz bağlamını serbest bırakır.

```cpp
void ReleaseDC() const throw();
```

### <a name="remarks"></a>Açıklamalar

Tek seferde bir cihaz bağlamına yalnızca bir bit eşlem seçilebildiğinden, `ReleaseDC` her [GetDC](#getdc)çağrısını çağırmanız gerekir.

## <a name="cimagereleasegdiplus"></a><a name="releasegdiplus"></a> CImage:: ReleaseGDIPlus

GDI+ tarafından kullanılan kaynakları serbest bırakır.

```cpp
void ReleaseGDIPlus() throw();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, genel bir nesne tarafından ayrılan kaynakları serbest bırakmak için çağrılmalıdır `CImage` . Bkz. [CImage:: CImage](#cimage).

## <a name="cimagesave"></a><a name="save"></a> CImage:: Save

Bir görüntüyü diskte belirtilen akışa veya dosyaya kaydeder.

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
Dosya görüntüsü verilerini içeren COM IStream nesnesine yönelik bir işaretçi.

*pszFileName*<br/>
Görüntü için dosya adı işaretçisi.

*guidFileType*<br/>
Görüntünün kaydedileceği dosya türü. Aşağıdakilerden biri olabilir:

- `ImageFormatBMP` Sıkıştırılmamış bir bit eşlem resmi.

- `ImageFormatPNG` Taşınabilir Ağ Grafiği (PNG) sıkıştırılmış görüntü.

- `ImageFormatJPEG` JPEG sıkıştırılmış görüntü.

- `ImageFormatGIF` GIF sıkıştırılmış görüntü.

> [!NOTE]
> Sabitlerin tamamen listesi için, bkz. Windows SDK **görüntü dosyası biçimi sabitleri** .

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Görüntüyü belirtilen bir ad ve tür kullanarak kaydetmek için bu işlevi çağırın. *GuidFileType* parametresi dahil edilmediğinden, görüntü biçimini belirlemekte dosya adının dosya uzantısı kullanılacaktır. Uzantı sağlanmazsa, görüntü BMP biçiminde kaydedilir.

## <a name="cimagesetcolortable"></a><a name="setcolortable"></a> CImage:: SetColorTable

DIB bölümünün paletindeki bir dizi giriş için kırmızı, yeşil, mavi (RGB) renk değerlerini ayarlar.

```cpp
void SetColorTable(
    UINT iFirstColor,
    UINT nColors,
    const RGBQUAD* prgbColors) throw();
```

### <a name="parameters"></a>Parametreler

*ıfırstcolor*<br/>
Ayarlanacak ilk girdinin renk tablosu dizini.

*Nrenkler*<br/>
Ayarlanacak renk tablosu girdilerinin sayısı.

*Prgbrenkler*<br/>
Renk tablosu girdilerini ayarlamak için [RGBQUAD](/windows/win32/api/wingdi/ns-wingdi-rgbquad) yapıları dizisine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca DIB bölümü bit eşlemlerini destekler.

## <a name="cimagesetpixel"></a><a name="setpixel"></a> CImage:: SetPixel

Bit eşlemdeki belirli bir konumdaki bir pikselin rengini ayarlar.

```cpp
void SetPixel(int x, int y, COLORREF color) throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Ayarlanacak pikselin yatay konumu.

*Iz*<br/>
Ayarlanacak pikselin dikey konumu.

*Renk*<br/>
Pikselin ayarlandığı renk.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, piksel koordinatları seçili kırpma bölgesinin dışında olursa başarısız olur.

## <a name="cimagesetpixelindexed"></a><a name="setpixelindexed"></a> CImage:: Setpixelındexed

Piksel rengini renk paletindeki *ıindex* konumunda bulunan renge ayarlar.

```cpp
void SetPixelIndexed(int x, int y, int iIndex) throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Ayarlanacak pikselin yatay konumu.

*Iz*<br/>
Ayarlanacak pikselin dikey konumu.

*IIndex*<br/>
Renk paletindeki bir rengin dizini.

## <a name="cimagesetpixelrgb"></a><a name="setpixelrgb"></a> CImage:: SetPixelRGB

*X* ve *y* ile belirtilen konumlardaki piksel, kırmızı, YEŞIL, mavi (RGB) görüntüde *r*, *g* ve *b* tarafından gösterilen renklerle ayarlanır.

```cpp
void SetPixelRGB(
    int x,
    int y,
    BYTE r,
    BYTE g,
    BYTE b) throw();
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Ayarlanacak pikselin yatay konumu.

*Iz*<br/>
Ayarlanacak pikselin dikey konumu.

*sağ*<br/>
Kırmızı rengin yoğunluğu.

*Acil*<br/>
Yeşil rengin yoğunluğu.

*kenarı*<br/>
Mavi rengin yoğunluğu.

### <a name="remarks"></a>Açıklamalar

Kırmızı, yeşil ve mavi parametrelerinin her biri 0 ile 255 arasında bir sayı ile temsil edilir. Üç parametreyi de sıfıra ayarlarsanız, elde edilen sonuç rengi siyah olur. Üç parametreyi de 255 olarak ayarlarsanız, birleştirilmiş sonuç rengi beyazdır.

## <a name="cimagesettransparentcolor"></a><a name="settransparentcolor"></a> CImage:: SetTransparentColor

Belirli bir dizinli konumdaki rengi saydam olarak ayarlar.

```
LONG SetTransparentColor(LONG iTransparentColor) throw();
```

### <a name="parameters"></a>Parametreler

*iTransparentColor*<br/>
Renk paletindeki, saydam olarak ayarlanacak olan dizin. -1 ise, hiçbir renk saydam olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Daha önce saydam olarak ayarlanmış rengin dizini.

## <a name="cimagestretchblt"></a><a name="stretchblt"></a> CImage:: uzatılabilir blt

Kaynak cihaz bağlamından bir bit eşlemi Bu geçerli cihaz bağlamına kopyalar.

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
Hedef cihaz bağlamına yönelik bir tanıtıcı.

*xDest*<br/>
Hedef dikdörtgenin sol üst köşesinin, mantıksal birimlerde x koordinatı.

*En dest*<br/>
Hedef dikdörtgenin sol üst köşesinin, mantıksal birimlerde y koordinatı.

*nDestWidth*<br/>
Hedef dikdörtgenin mantıksal birimlerindeki genişliği.

*nDestHeight*<br/>
Hedef dikdörtgenin mantıksal birimleri cinsinden yüksekliği.

*dwROP*<br/>
Gerçekleştirilecek tarama işlemi. Raster-işlem kodları, hedefi oluşturmak için kaynak, hedef ve düzenin bitlerini (Şu anda seçili fırça tarafından tanımlanan şekilde) tam olarak nasıl birleştirileceğini tanımlar. Diğer raster işlem kodlarının listesi ve açıklamaları için Windows SDK [BitBlt](/windows/win32/api/wingdi/nf-wingdi-bitblt) ' i inceleyin.

*rectDest*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına bir başvuru, hedefi tanımlar.

*xSrc*<br/>
Kaynak dikdörtgenin sol üst köşesinin, mantıksal birimlerde x koordinatı.

*ySrc*<br/>
Kaynak dikdörtgenin sol üst köşesinin, mantıksal birimlerde y koordinatı.

*nSrcWidth*<br/>
Kaynak dikdörtgenin mantıksal birimlerindeki genişliği.

*nSrcHeight*<br/>
Kaynak dikdörtgenin mantıksal birimleri cinsinden yüksekliği.

*rectSrc*<br/>
`RECT`Kaynağı tanımlayarak bir yapıya başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK [için bkz.](/windows/win32/api/wingdi/nf-wingdi-stretchblt) .

## <a name="cimagetransparentblt"></a><a name="transparentblt"></a> CImage:: TransparentBlt

Kaynak cihaz bağlamından bir bit eşlemi Bu geçerli cihaz bağlamına kopyalar.

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
Hedef cihaz bağlamına yönelik bir tanıtıcı.

*xDest*<br/>
Hedef dikdörtgenin sol üst köşesinin, mantıksal birimlerde x koordinatı.

*En dest*<br/>
Hedef dikdörtgenin sol üst köşesinin, mantıksal birimlerde y koordinatı.

*nDestWidth*<br/>
Hedef dikdörtgenin mantıksal birimlerindeki genişliği.

*nDestHeight*<br/>
Hedef dikdörtgenin mantıksal birimleri cinsinden yüksekliği.

*crTransparent*<br/>
Saydam olarak değerlendirmek için kaynak bit eşlemdeki renk. Varsayılan olarak, görüntünün saydam rengi olarak ayarlanmış rengin kullanılması gerektiğini belirten CLR_INVALID.

*rectDest*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına bir başvuru, hedefi tanımlar.

*xSrc*<br/>
Kaynak dikdörtgenin sol üst köşesinin, mantıksal birimlerde x koordinatı.

*ySrc*<br/>
Kaynak dikdörtgenin sol üst köşesinin, mantıksal birimlerde y koordinatı.

*nSrcWidth*<br/>
Kaynak dikdörtgenin mantıksal birimlerindeki genişliği.

*nSrcHeight*<br/>
Kaynak dikdörtgenin mantıksal birimleri cinsinden yüksekliği.

*rectSrc*<br/>
`RECT`Kaynağı tanımlayarak bir yapıya başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE, aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

`TransparentBlt` piksel başına 4 bit ve piksel başına 8 bit olan kaynak bit eşlemler için desteklenir. Saydamlığı olan 32 bitlik bit eşlemler belirtmek için [CImage:: harflerden Blend](#alphablend) kullanın.

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

[Mmxsısınma örneği](../../overview/visual-cpp-samples.md)<br/>
[SimpleImage örneği](../../overview/visual-cpp-samples.md)<br/>
[Cihazdan bağımsız bit eşlemler](/windows/win32/gdi/device-independent-bitmaps)<br/>
[CreateDIBSection](/windows/win32/api/wingdi/nf-wingdi-createdibsection)<br/>
[ATL COM Masaüstü Bileşenleri](../../atl/atl-com-desktop-components.md)<br/>
[Cihazdan bağımsız bit eşlemler](/windows/win32/gdi/device-independent-bitmaps)<br/>
[CreateDIBSection](/windows/win32/api/wingdi/nf-wingdi-createdibsection)
