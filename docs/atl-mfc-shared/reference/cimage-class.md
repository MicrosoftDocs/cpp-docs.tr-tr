---
title: Cımage sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 02/01/2018
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 762941834820edda09970750af752d4c8a9df61c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366321"
---
# <a name="cimage-class"></a>Cımage sınıfı
`CImage` Yük ve görüntüleri JPEG, GIF, BMP ve Taşınabilir Ağ Grafikleri (PNG) biçimlerde kaydetme özelliği de dahil olmak üzere Gelişmiş bit eşlem desteği sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
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
|[CImage::AlphaBlend](#alphablend)|Saydam veya yarı saydam piksel sahip bit eşlemler görüntüler.|  
|[CImage::Attach](#attach)|Bağlayan bir `HBITMAP` için bir `CImage` nesnesi. DIB olmayan bölüm bit eşlemler veya DIB bölüm bit eşlemler ile kullanılabilir.|  
|[CImage::BitBlt](#bitblt)|Bir bit eşlem kaynak aygıt bağlamından geçerli bu cihaz bağlamı kopyalar.|  
|[CImage::Create](#create)|DIB bölüm bit eşlem oluşturur ve daha önce oluşturulan iliştirir `CImage` nesnesi.|  
|[CImage::CreateEx](#createex)|DIB bölüm bit eşlem (ek parametreleriyle birlikte) oluşturur ve daha önce oluşturulan iliştirir `CImage` nesnesi.|  
|[CImage::Destroy](#destroy)|Bit eşlem ayırır `CImage` nesne ve bit eşlem yok eder.|  
|[CImage::Detach](#detach)|Bit eşlem ayırır bir `CImage` nesnesi.|  
|[CImage::Draw](#draw)|Bir bit eşlem kaynak dikdörtgene hedef dikdörtgene kopyalar. **Çizim** uzatır veya hedef dikdörtgenin gerekirse boyutlarına bit eşlem sıkıştırır ve Alfa karışım ve saydam renkleri işler.|  
|[CImage::GetBits](#getbits)|Bit eşlem gerçek piksel değerlerini gösteren bir işaretçi alır.|  
|[CImage::GetBPP](#getbpp)|Bit / piksel alır.|  
|[CImage::GetColorTable](#getcolortable)|Kırmızı, yeşil, mavi (RGB) renk değerleri bir renk tablosundaki girişleri aralığını alır.|  
|[CImage::GetDC](#getdc)|Geçerli bit eşlem üzerine seçili cihaz bağlamı alır.|  
|[CImage::GetExporterFilterString](#getexporterfilterstring)|Kullanılabilir resim biçimleri ve açıklamalarının bulur.|  
|[CImage::GetHeight](#getheight)|Geçerli görüntü piksel cinsinden yüksekliği alır.|  
|[CImage::GetImporterFilterString](#getimporterfilterstring)|Kullanılabilir resim biçimleri ve açıklamalarının bulur.|  
|[CImage::GetMaxColorTableEntries](#getmaxcolortableentries)|Renk tablosunda giriş sayısı üst sınırı alır.|  
|[CImage::GetPitch](#getpitch)|Bayt cinsinden geçerli görüntü aralığını alır.|  
|[CImage::GetPixel](#getpixel)|Tarafından belirtilen piksel rengi alır *x* ve *y*.|  
|[CImage::GetPixelAddress](#getpixeladdress)|Verilen piksel adresini alır.|  
|[CImage::GetTransparentColor](#gettransparentcolor)|Renk tablosu saydam rengi konumunu alır.|  
|[CImage::GetWidth](#getwidth)|Geçerli görüntü piksel cinsinden genişliği alır.|  
|[CImage::IsDIBSection](#isdibsection)|Ekli bit eşlem DIB bölüm olup olmadığını belirler.|  
|[CImage::IsIndexed](#isindexed)|Bit eşlem 's renkler için dizinlenmiş palet eşlenmiş gösterir.|  
|[CImage::IsNull](#isnull)|Kaynak bitmap yüklü olmadığını gösterir.|  
|[CImage::IsTransparencySupported](#istransparencysupported)|Uygulama saydam bit eşlemler destekleyip desteklemediğini belirtir.|  
|[CImage::Load](#load)|Görüntüyü belirtilen dosyadan yükler.|  
|[CImage::LoadFromResource](#loadfromresource)|Görüntüyü belirtilen kaynak yükler.|  
|[CImage::MaskBlt](#maskblt)|Belirtilen maske ve Tarama işlemi kullanarak kaynak ve hedef bit eşlemler renk verilerini bir araya getirir.|  
|[CImage::PlgBlt](#plgblt)|Bit bloğu aktarımı bir paralel kenarı bir hedef cihaz bağlamda içine dikdörtgenden kaynak aygıt bağlamda gerçekleştirir.|  
|[CImage::ReleaseDC](#releasedc)|İle alınan cihaz bağlamı serbest [CImage::GetDC](#getdc).|  
|[CImage::ReleaseGDIPlus](#releasegdiplus)|GDI + tarafından kullanılan kaynakları serbest bırakır. Genel tarafından oluşturulan kaynakları serbest bırakmak için çağrılmalıdır `CImage` nesnesi.|  
|[CImage::Save](#save)|Görüntüyü belirtilen tür olarak kaydeder. **Kaydet** görüntü seçenekleri belirtemezsiniz.|  
|[CImage::SetColorTable](#setcolortable)|Kırmızı, yeşil, mavi RGB ayarlar) renk DIB bölümünün renk tablosundaki girişleri aralığındaki değerler.|  
|[CImage::SetPixel](#setpixel)|Belirtilen renk belirtilen koordinatları adresindeki piksel ayarlar.|  
|[CImage::SetPixelIndexed](#setpixelindexed)|Renk paleti belirtilen dizindeki belirtilen koordinatları adresindeki piksel ayarlar.|  
|[CImage::SetPixelRGB](#setpixelrgb)|Belirtilen kırmızı, yeşil, mavi (RGB) değeri belirtilen koordinatları adresindeki piksel ayarlar.|  
|[CImage::SetTransparentColor](#settransparentcolor)|Kabul edilmesi için renk dizinini saydam olarak ayarlar. Yalnızca bir renk paleti saydam olabilir.|  
|[CImage::StretchBlt](#stretchblt)|Bir bit eşlem kaynak dikdörtgene uzatma veya gerekirse hedef dikdörtgenin boyutlarına bit eşlem sıkıştırma hedef dikdörtgen kopyalar.|  
|[CImage::TransparentBlt](#transparentblt)|Saydam rengi bir bit eşlem kaynak aygıt bağlamından geçerli bu cihaz bağlamı kopyalar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CImage::operator HBITMAP](#operator_hbitmap)|Bağlı Windows işleyici döner `CImage` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CImage` Her iki CİHAZDAN bağımsız bit eşlem (DIB) bölümleri olsun bit eşlemler alır; Ancak, kullanabileceğiniz [oluşturma](#create) veya [CImage::Load](#load) yalnızca DIB bölümleri ile. DIB olmayan bölüm bit eşlem için iliştirebilirsiniz bir `CImage` kullanarak nesne [Attach](#attach), ancak aşağıdaki sonra kullanamazsınız `CImage` yalnızca DIB bölüm bit eşlemler destek yöntemleri:  
  
- [GetBits](#getbits)  
  
- [GetColorTable](#getcolortable)  
  
- [GetMaxColorTableEntries](#getmaxcolortableentries)  
  
- [GetPitch](#getpitch)  
  
- [GetPixelAddress](#getpixeladdress)  
  
- [IsIndexed](#isindexed)  
  
- [SetColorTable](#setcolortable)  
  
 Ekli bir bit eşlem DIB bölüm olup olmadığını belirlemek için arama [IsDibSection](#isdibsection)**.**  
  
> [!NOTE]
> **Not** , Visual Studio .NET 2003, bu sınıfın tutar sayısını sayısını `CImage` oluşturulan nesneler. Sayı 0, işlevi her gider **GdiplusShutdown** GDI + tarafından kullanılan kaynakları serbest bırakmak için otomatik olarak çağrılır. Bu, herhangi bir sağlar `CImage` doğrudan veya dolaylı olarak DLL'leri tarafından oluşturulan nesneler her zaman kaybolur düzgün ve **GdiplusShutdown** gelen çağrılmaz `DllMain`.  
  
> [!NOTE]
>  Genel kullanarak `CImage` DLL nesneleri önerilmez. Bir genel kullanmanız gerekiyorsa `CImage` bir DLL çağrı nesnesinde [CImage::ReleaseGDIPlus](#releasegdiplus) açıkça GDI + tarafından kullanılan kaynakları serbest bırakmak için.  
  
 `CImage` Yeni bir seçilemez [CDC](../../mfc/reference/cdc-class.md). `CImage` kendi oluşturur **HDC** görüntü için. Çünkü bir `HBITMAP` birine yalnızca seçilebilir **HDC** , her seferinde `HBITMAP` ile ilişkili `CImage` başka bir dosyaya seçilemez **HDC**. Gerekirse bir `CDC`, almak **HDC** gelen `CImage` ve [CDC::FromHandle] verin (.. /.. /MFC/Reference/cdc-class.MD#cdc__fromhandle.  
  
## <a name="example"></a>Örnek  
```cpp  
// Get a CDC for the image
CDC* pDC = CDC::FromHandle(m_myImage.GetDC());

// Use pDC here
pDC->Rectangle(0, 40, 100, 50);
m_myImage.ReleaseDC();
```  
  
 Kullandığınızda `CImage` MFC projesinde, hangi üye işlevleri projenizdeki gösteren bir işaretçi beklediğini unutmayın bir [CBitmap](../../mfc/reference/cbitmap-class.md) nesnesi. Kullanmak istiyorsanız, `CImage` böyle bir işlevi olan gibi [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu), kullanın [CBitmap::FromHandle](../../mfc/reference/cbitmap-class.md#fromhandle), onu geçirmek, `CImage` `HBITMAP`ve döndürülen `CBitmap*`.  

  
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

  
 Aracılığıyla `CImage`, gerçek BITS DIB bölümün erişimi. Kullanabileceğiniz bir `CImage` herhangi bir yere Win32 HBITMAP veya DIB bölümünde daha önce kullanılan nesne.  
  
 Kullanabileceğiniz `CImage` MFC veya ATL  
  
> [!NOTE]
>  Kullanarak bir proje oluşturduğunuzda `CImage`, tanımlamanız gerekir `CString` dahil önce `atlimage.h`. Projenize ATL MFC olmadan kullanıyorsa, dahil `atlstr.h` dahil önce `atlimage.h`. Projeniz MFC (veya ATL projesinde MFC desteği olup olmadığını) kullanıyorsa, dahil `afxstr.h` dahil önce `atlimage.h`.  
>   
>  Benzer şekilde, içermelidir `atlimage.h` dahil önce `atlimpl.cpp`. Bunu kolayca gerçekleştirmek için dahil `atlimage.h` içinde `stdafx.h`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlimage.h  
  
##  <a name="alphablend"></a>  CImage::AlphaBlend  
 Saydam veya yarı saydam piksel sahip bit eşlemler görüntüler.  
  
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
 `hDestDC`  
 Hedef cihaz bağlamına işleyin.  
  
 `xDest`  
 X koordinatını, mantıksal birimlerini, hedef dikdörtgenin sol üst köşesinin.  
  
 `yDest`  
 Y koordinatını, mantıksal birimlerini, hedef dikdörtgenin sol üst köşesinin.  
  
 *bSrcAlpha*  
 Tüm kaynak bitmap üzerinde kullanılacak bir alfa saydamlığı değeri. Varsayılan 0xff (255) görüntünüzü donuk olduğunu ve yalnızca alfa değerleri piksel başına kullanmak istediğinizi varsayar.  
  
 `bBlendOp`  
 Alfa karıştırma işlevi için kaynak ve hedef bit eşlemler, tüm kaynak bitmap ve kaynak bit eşlem biçimi bilgileri uygulanacak genel alfa değeri. Kaynak ve hedef karışım işlevleri için şu anda sınırlı **AC_SRC_OVER**.  
  
 `pointDest`  
 Bir başvuru bir [noktası](http://msdn.microsoft.com/library/windows/desktop/dd162805) hedef dikdörtgende mantıksal birimler sol üst köşesinin tanımlayan yapısı.  
  
 `nDestWidth`  
 Mantıksal birimleri, hedef dikdörtgenin genişliği.  
  
 `nDestHeight`  
 Hedef dikdörtgenin mantıksal birimler yüksekliği.  
  
 `xSrc`  
 Kaynak dikdörtgenin sol üst köşesinin mantıksal x-koordinatı.  
  
 `ySrc`  
 Kaynak dikdörtgenin sol üst köşesinin mantıksal y-koordinatı.  
  
 `nSrcWidth`  
 Mantıksal birimleri, kaynak dikdörtgenin genişliği.  
  
 `nSrcHeight`  
 Kaynak dikdörtgenin mantıksal birimler yüksekliği.  
  
 `rectDest`  
 Bir başvuru bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı, hedef belirleme.  
  
 `rectSrc`  
 Bir başvuru bir `RECT` kaynağını tanımlayan yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Alfa karışım bit eşlemler piksel başına temelinde renk karıştırma destekler.  
  
 Zaman `bBlendOp` varsayılan olarak ayarla **AC_SRC_OVER**, kaynak bitmap kaynak piksel alfa değerlerine göre hedef bit eşlem üzerinden yerleştirilir.  

##  <a name="attach"></a>  CImage::Attach  
 İliştirir `hBitmap` için bir `CImage` nesnesi.  
  
```
void Attach(HBITMAP hBitmap, DIBOrientation eOrientation = DIBOR_DEFAULT) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `hBitmap`  
 İçin bir tanıtıcı bir `HBITMAP`.  
  
 *eOrientation*  
 Bit eşlem yönünü belirtir. Aşağıdakilerden biri olabilir:  
  
- **DIBOR_DEFAULT** bit eşlem yönünü işletim sistemi tarafından belirlenir. Ancak, bu her zaman amaçlı sonuçları tüm işletim sistemlerine sahip olmayabilir. Bunun hakkında daha fazla bilgi için aşağıdaki Bilgi Bankası makalesine bakın ( **Q186586**): sorun: GetObject() her zaman döndürür pozitif yüksekliği için DIB bölümler.  
  
- **DIBOR_BOTTOMUP** satırlık bir bit eşlem ters sıradadır. Bu neden olur [CImage::GetBits](#getbits) bit eşlem arabelleğin sonuna imlecini dönün ve [CImage::GetPitch](#getpitch) negatif bir sayı dönün.  
  
- **DIBOR_TOPDOWN** alt sipariş dön satırlık bir bit eşlem bulunan. Bu neden [CImage::GetBits](#getbits) bit eşlem arabellek ilk bayta kalan için bir işaretçi döndürmek için ve [CImage::GetPitch](#getpitch) pozitif bir sayı dönün.  
  
### <a name="remarks"></a>Açıklamalar  
 Bit eşlem DIB olmayan bölüm bit eşlem veya DIB bölüm bit eşlem olabilir. Bkz: [IsDIBSection](#isdibsection) yalnızca DIB ile kullanabileceğiniz yöntemler listesi için bit eşlemler bölüm.  
  
##  <a name="bitblt"></a>  CImage::BitBlt  
 Bir bit eşlem kaynak aygıt bağlamından geçerli bu cihaz bağlamı kopyalar.  
  
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
 `hDestDC`  
 Hedef **HDC**.  
  
 `xDest`  
 Hedef dikdörtgenin sol üst köşesinin mantıksal x-koordinatı.  
  
 `yDest`  
 Mantıksal y koordinatını hedef dikdörtgenin sol üst köşesinin.  
  
 `dwROP`  
 Gerçekleştirilecek tarama işlemi. Tarama işlemi kodları kaynak, hedef ve desen BITS (şu anda seçili fırça tarafından tanımlandığı gibi) hedef oluşturmak için tam olarak nasıl birleştirileceğini tanımlar. Bkz: [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) diğer tarama işlemi kodları ve açıklamaları listesi için Windows SDK.  
  
 `pointDest`  
 A [noktası](http://msdn.microsoft.com/library/windows/desktop/dd162805) hedef dikdörtgenin sol üst köşesinin belirten yapısı.  
  
 `nDestWidth`  
 Mantıksal birimleri, hedef dikdörtgenin genişliği.  
  
 `nDestHeight`  
 Hedef dikdörtgenin mantıksal birimler yüksekliği.  
  
 `xSrc`  
 Kaynak dikdörtgenin sol üst köşesinin mantıksal x-koordinatı.  
  
 `ySrc`  
 Kaynak dikdörtgenin sol üst köşesinin mantıksal y-koordinatı.  
  
 `rectDest`  
 A [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) hedef dikdörtgen belirten yapısı.  
  
 `pointSrc`  
 A **noktası** kaynak dikdörtgenin sol üst köşesinin belirten yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) Windows SDK'sındaki.  
  
##  <a name="cimage"></a>  CImage::CImage  
 Oluşturan bir `CImage` nesnesi.  
  
```
CImage() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne oluşturulan sonra çağrısı [oluşturma](#create), [yük](#load), [LoadFromResource](#loadfromresource), veya [Attach](#attach) nesnesine bir bit eşlem eklemek için.  
  
 **Not** Visual Studio'da, bu sınıfın tutar sayısını sayısını `CImage` oluşturulan nesneler. Sayı 0, işlevi her gider **GdiplusShutdown** GDI + tarafından kullanılan kaynakları serbest bırakmak için otomatik olarak çağrılır. Bu, herhangi bir sağlar `CImage` doğrudan veya dolaylı olarak DLL'leri tarafından oluşturulan nesneler her zaman kaybolur düzgün ve **GdiplusShutdown** DllMain çağrılmaz.  
  
 Genel kullanarak `CImage` DLL nesneleri önerilmez. Bir genel kullanmanız gerekiyorsa `CImage` bir DLL çağrı nesnesinde [CImage::ReleaseGDIPlus](#releasegdiplus) açıkça GDI + tarafından kullanılan kaynakları serbest bırakmak için.  
  
##  <a name="create"></a>  CImage::Create  
 Oluşturur bir `CImage` bit eşlem ve daha önce oluşturulan ekleme `CImage` nesnesi.  
  
```
BOOL Create(
 int nWidth,
 int nHeight,
 int nBPP,
 DWORD dwFlags = 0) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nWidth`  
 Genişliğini `CImage` piksel cinsinden bitmap.  
  
 `nHeight`  
 Yüksekliğini `CImage` piksel cinsinden bitmap. Varsa `nHeight` bit eşlem aşağıdan yukarıya DIB ve kendi başlangıç sol alt köşesinde pozitif. Varsa `nHeight` , bit eşlem yukarıdan aşağıya DIB negatifse ve sol üst köşedeki kaynağına ise.  
  
 `nBPP`  
 Bit eşlem piksel sayısı. Genellikle 4, 8, 16, 24 veya 32. 1 bitmap veya maskeleri olabilir.  
  
 `dwFlags`  
 Bit eşlem nesne alfa kanal olup olmadığını belirtir. Bir bileşimi sıfır veya daha fazla aşağıdaki değerlerden biri olabilir:  
  
- **createAlphaChannel** varsa kullanılabilir `nBPP` , 32'dir ve `eCompression` olan **BI_RGB**. Belirtilmişse, oluşturulan görüntü her piksel (alfasayısal olmayan 32 bit bir görüntü kullanılmayan) 4 baytlık depolanan her piksel için bir alfa (Saydamlık) değere sahip. Bu alfa kanal otomatik olarak çağrılırken kullanılan [CImage::AlphaBlend](#alphablend).  
  
> [!NOTE]
>  Çağrılarında [CImage::Draw](#draw), alfa kanalı ile görüntüleri otomatik olarak alfa hedefe karıştırılan.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="createex"></a>  CImage::CreateEx  
 Oluşturur bir `CImage` bit eşlem ve daha önce oluşturulan ekleme `CImage` nesnesi.  
  
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
 `nWidth`  
 Genişliğini `CImage` piksel cinsinden bitmap.  
  
 `nHeight`  
 Yüksekliğini `CImage` piksel cinsinden bitmap. Varsa `nHeight` bit eşlem aşağıdan yukarıya DIB ve kendi başlangıç sol alt köşesinde pozitif. Varsa `nHeight` , bit eşlem yukarıdan aşağıya DIB negatifse ve sol üst köşedeki kaynağına ise.  
  
 `nBPP`  
 Bit eşlem piksel sayısı. Genellikle 4, 8, 16, 24 veya 32. 1 bitmap veya maskeleri olabilir.  
  
 `eCompression`  
 (Yukarıdan aşağı DIB'leri sıkıştırılamaz) sıkıştırılmış bir aşağıdan yukarıya bit eşlem sıkıştırma türünü belirtir. Aşağıdaki değerlerden biri olabilir:  
  
- **BI_RGB** sıkıştırılmamış bir biçimidir. Çağrılırken bu değeri belirterek `CImage::CreateEx` arama için eşdeğer bir gruba `CImage::Create`.  
  
- **BI_BITFIELDS** sıkıştırılmamış bir biçimidir ve renk tablosu üç oluşur `DWORD` kırmızı belirtin renk maskeleri yeşil ve bileşenleri, sırasıyla her pikseli mavi. Bu 16 ve 32 bpp bit eşlemler ile kullanıldığında geçerlidir.  
  
 *pdwBitfields*  
 Yalnızca, kullanılan `eCompression` ayarlanır **BI_BITFIELDS**, aksi halde olmalıdır **NULL**. Üç bir dizi için bir işaretçi `DWORD` her piksel hangi bitleri kırmızı için kullanılan belirten bir bit maskesi, yeşil ve renk bileşenlerinin sırasıyla mavi. Bit alanları için kısıtlamaları hakkında daha fazla bilgi için bkz: [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) Windows SDK'sındaki.  
  
 `dwFlags`  
 Bit eşlem nesne alfa kanal olup olmadığını belirtir. Bir bileşimi sıfır veya daha fazla aşağıdaki değerlerden biri olabilir:  
  
- **createAlphaChannel** varsa kullanılabilir `nBPP` , 32'dir ve `eCompression` olan **BI_RGB**. Belirtilmişse, oluşturulan görüntü her piksel (alfasayısal olmayan 32 bit bir görüntü kullanılmayan) 4 baytlık depolanan her piksel için bir alfa (Saydamlık) değere sahip. Bu alfa kanal otomatik olarak çağrılırken kullanılan [CImage::AlphaBlend](#alphablend).  
  
    > [!NOTE]
    >  Çağrılarında [CImage::Draw](#draw), alfa kanalı ile görüntüleri otomatik olarak alfa hedefe karıştırılan.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** başarılı olursa. Aksi takdirde **FALSE**.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, her piksel kodlamak için 16 bit kullanarak bir 100 x 100 piksel bit eşlem oluşturur. Belirli bir 16 bit piksel 0-3 bitleri kırmızı bileşenini kodlamak ve BITS 4-7 yeşil kodlamak BITS 8-11 mavi kodlayın. Kalan 4 kullanılmayan bittir.  

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
 Bir bit eşlem ayırır bir `CImage` nesnesi.  
  
```
HBITMAP Detach() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrılmış, bit eşlem için bir tanıtıcı veya **NULL** hiçbir bit eşlem bağlıysa.  
  
##  <a name="draw"></a>  CImage::Draw  
 Bir bit eşlem kaynak aygıt bağlamından geçerli cihaz bağlamı kopyalar.  
  
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
 `hDestDC`  
 Hedef cihaz bağlamı için bir tanıtıcı.  
  
 `xDest`  
 X koordinatını, mantıksal birimlerini, hedef dikdörtgenin sol üst köşesinin.  
  
 `yDest`  
 Y koordinatını, mantıksal birimlerini, hedef dikdörtgenin sol üst köşesinin.  
  
 `nDestWidth`  
 Mantıksal birimleri, hedef dikdörtgenin genişliği.  
  
 `nDestHeight`  
 Hedef dikdörtgenin mantıksal birimler yüksekliği.  
  
 `xSrc`  
 X koordinatını, kaynak dikdörtgenin sol üst köşesinin, mantıksal birimler.  
  
 `ySrc`  
 Y koordinatını, kaynak dikdörtgenin sol üst köşesinin, mantıksal birimler.  
  
 `nSrcWidth`  
 Mantıksal birimleri, kaynak dikdörtgenin genişliği.  
  
 `nSrcHeight`  
 Kaynak dikdörtgenin mantıksal birimler yüksekliği.  
  
 `rectDest`  
 Bir başvuru bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı, hedef belirleme.  
  
 `rectSrc`  
 Bir başvuru bir `RECT` kaynağını tanımlayan yapısı.  
  
 `pointDest`  
 Bir başvuru bir [noktası](http://msdn.microsoft.com/library/windows/desktop/dd162805) hedef dikdörtgende mantıksal birimler sol üst köşesinin tanımlayan yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 **Çizim** olarak aynı işlemi gerçekleştirir [StretchBlt](#stretchblt), resmin saydam rengini veya alfa kanal içermiyorsa. Bu durumda, **çizin** olarak ya da aynı işlemi gerçekleştirir [TransparentBlt](#transparentblt) veya [AlphaBlend](#alphablend) gerektiği gibi.  
  
 Sürümleri için **çizin** kaynak dikdörtgen belirlemezseniz, tüm kaynak görüntü varsayılandır. Sürümü için **çizin** hedef dikdörtgen için bir boyut belirtmiyor, kaynak görüntü boyutu varsayılan ve hiçbir uzatma ya da küçültme oluşur.  
  
##  <a name="getbits"></a>  CImage::GetBits  
 Bir işaretçi eşlemde belirli bir piksel gerçek bit değerlerini alır.  
  
```
void* GetBits() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bit eşlem arabellek için bir işaretçi. Bit eşlem aşağıdan yukarıya DIB ise, işaretçi noktaları arabelleğin sonuna yakınında. Bit eşlem yukarıdan aşağıya DIB ise, işaretçi arabellek ilk bayta işaret eder.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından döndürülen değer yanı sıra bu işaretçisi kullanılarak [GetPitch](#getpitch), bulun ve tek tek piksel cinsinden görüntü ile değiştirin.  
  
> [!NOTE]
>  Bu yöntem yalnızca DIB bölüm bit eşlemler destekler; Sonuç olarak, size piksel erişim bir `CImage` DIB bölüm piksel olduğu gibi nesne. (0, 0) konumundaki piksel döndürülen işaretçisi işaret ediyor.  
  
##  <a name="getbpp"></a>  CImage::GetBPP  
 Bit / piksel değerini alır.  
  
```
int GetBPP() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bit / piksel sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değer, her piksel tanımlamak bit sayısını ve bit eşlem renkleri üst sınırını belirler.  
  
 Bit / piksel olan genellikle 1, 4, 8, 16, 24 veya 32. Bkz: **biBitCount** üyesi [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) bu değeri hakkında daha fazla bilgi için Windows SDK'sındaki.  
  
##  <a name="getcolortable"></a>  CImage::GetColorTable  
 Kırmızı, yeşil, mavi (RGB) renk değerleri DIB bölümünün paleti girdileri aralığını alır.  
  
```
void GetColorTable(UINT iFirstColor,
 UINT nColors,
 RGBQUAD* prgbColors) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `iFirstColor`  
 İlk giriş almak için renk tablosu dizini.  
  
 `nColors`  
 Almak için renk tablosu girdileri sayısı.  
  
 `prgbColors`  
 Dizi için bir işaretçi [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) rengi almak için yapıları tablo girişleri.  
  
##  <a name="getdc"></a>  CImage::GetDC  
 Şu anda içine seçili resimle cihaz bağlamı alır.  
  
```
HDC GetDC() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir cihaz bağlamı için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Her çağrı için `GetDC`, bir sonraki çağrı olmalıdır [ReleaseDC](#releasedc).  
  
##  <a name="getexporterfilterstring"></a>  CImage::GetExporterFilterString  
 Görüntüleri kaydetmek için kullanılabilir görüntü biçimleri bulur.  
  
```
static HRESULT GetExporterFilterString(CSimpleString& strExporters,
 CSimpleArray<GUID>& aguidFileTypes,
 LPCTSTR pszAllFilesDescription = NULL,
 DWORD dwExclude = excludeDefaultSave,
 TCHAR chSeparator = _T('|'));
```  
  
### <a name="parameters"></a>Parametreler  
 *strExporters*  
 Bir başvuru bir **CSimpleString** nesnesi. Bkz: **açıklamalar** daha fazla bilgi için.  
  
 `aguidFileTypes`  
 GUID, bir dizi dizesindeki dosya türlerinden birini karşılık gelen her öğeye sahip. Örnekte `pszAllFilesDescription` aşağıdaki `aguidFileTypes`[0] olan `GUID_NULL` ve geçerli işletim sistemi tarafından desteklenen görüntü dosyası biçimlerini kalan dizi değerlerdir.  
  
> [!NOTE]
>  Sabitler tam bir listesi için bkz: **görüntü dosya biçimi sabitleri** Windows SDK'sındaki.  
  
 `pszAllFilesDescription`  
 Bu parametre değilse **NULL**, filtre dizesi bir ek filtre listenin başında sahip olur. Bu filtre geçerli değeri olur `pszAllFilesDescription` , açıklaması ve diğer dışarı aktarma listesindeki tarafından desteklenen herhangi bir genişletme dosya kabul eder.  
  
 Örneğin:  

```cpp  
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any exporter.
CImage::GetExporterFilterString(
    strExporters, aguidFileTypes, 
 _T("All Image Files"));
```  

  
 `dwExclude`  
 Bit bayrakları listeden dışlamak için hangi dosya türlerini belirtme kümesi. İzin verilen bayraklar şunlardır:  
  
- **excludeGIF** 0x01 dışlar GIF dosyaları =.  
  
- **excludeBMP** 0x02 dışlar BMP (Windows bit eşlem) dosyaları =.  
  
- **excludeEMF** 0x04 dışlar EMF (geliştirilmiş meta dosyası) dosyaları =.  
  
- **excludeWMF** 0x08 dışlar WMF (Windows Meta dosyası) dosyaları =.  
  
- **excludeJPEG** 0x10 dışlar JPEG dosyaları =.  
  
- **excludePNG** 0x20 dışlar PNG dosyaları =.  
  
- **excludeTIFF** 0x40 dışlar TIFF dosyaları =.  
  
- **excludeIcon** 0x80 dışlar ICO (Windows simgesi) dosyaları =.  
  
- **excludeOther** = 0x80000000 Yukarıda listelenmeyen başka bir dosya türü dışlar.  
  
- **excludeDefaultLoad** = 0 yük, tüm dosya türleri varsayılan olarak dahil  
  
- **excludeDefaultSave** = **excludeIcon &#124; excludeEMF &#124; excludeWMF** genellikle sahip oldukları özel gereksinimler için kaydetme için bu dosyalar varsayılan olarak dışarıda bırakılır.  
  
 `chSeparator`  
 Görüntü biçimleri arasında kullanılan ayırıcı. Bkz: **açıklamalar** daha fazla bilgi için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
### <a name="remarks"></a>Açıklamalar  
 MFC ile elde edilen biçim dizesi geçirebilirsiniz [CFileDialog](../../mfc/reference/cfiledialog-class.md) kullanılabilir görüntünün dosya uzantılarını kullanıma sunmak için nesneyi Dosya Kaydet iletişim kutusunda biçimlendirir.  
  
 Parametre *strExporter* biçime sahiptir:  
  
 description0 dosya&#124;\*.ext0&#124;filedescription1&#124;\*.ext1&#124;.. .file açıklama *n*&#124;\*.Ext .ext *n*&#124;&#124;  
  
 Burada '&#124;' ayırıcı karakteri tarafından belirtilen `chSeparator`. Örneğin:  
  
 `"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`  
  
 Varsayılan ayırıcı kullan '&#124;' Bu dize bir MFC geçirirseniz `CFileDialog` nesnesi. Ortak Dosya Kaydet iletişim kutusu için bu dizeyi geçirirseniz null ayırıcı '\0' kullanın.  
  
##  <a name="getheight"></a>  CImage::GetHeight  
 Piksel cinsinden görüntü yüksekliği alır.  
  
```
int GetHeight() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Piksel cinsinden görüntü yüksekliği.  
  
##  <a name="getimporterfilterstring"></a>  CImage::GetImporterFilterString  
 Görüntü biçimlerini kullanılabilir görüntülerin yüklenmesini bulur.  
  
```
static HRESULT GetImporterFilterString(CSimpleString& strImporters,
 CSimpleArray<GUID>& aguidFileTypes,
 LPCTSTR pszAllFilesDescription = NULL,
 DWORD dwExclude = excludeDefaultLoad,
 TCHAR chSeparator = _T('|'));
```  
  
### <a name="parameters"></a>Parametreler  
 *strImporters*  
 Bir başvuru bir **CSimpleString** nesnesi. Bkz: **açıklamalar** daha fazla bilgi için.  
  
 `aguidFileTypes`  
 GUID, bir dizi dizesindeki dosya türlerinden birini karşılık gelen her öğeye sahip. Örnekte `pszAllFilesDescription` aşağıdaki `aguidFileTypes`[0] olan `GUID_NULL` kalan diziyle geçerli işletim sistemi tarafından desteklenen görüntü dosyası biçimlerini değerlerdir.  
  
> [!NOTE]
>  Sabitler tam bir listesi için bkz: **görüntü dosya biçimi sabitleri** Windows SDK'sındaki.  
  
 `pszAllFilesDescription`  
 Bu parametre değilse **NULL**, filtre dizesi bir ek filtre listenin başında sahip olur. Bu filtre geçerli değeri olur `pszAllFilesDescription` , açıklaması ve diğer dışarı aktarma listesindeki tarafından desteklenen herhangi bir genişletme dosya kabul eder.  
  
 Örneğin:  

```cpp  
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any importer.
CImage::GetImporterFilterString(
    strImporters, aguidFileTypes, 
 _T("All Image Files"));
```  

  
 `dwExclude`  
 Bit bayrakları listeden dışlamak için hangi dosya türlerini belirtme kümesi. İzin verilen bayraklar şunlardır:  
  
- **excludeGIF** 0x01 dışlar GIF dosyaları =.  
  
- **excludeBMP** 0x02 dışlar BMP (Windows bit eşlem) dosyaları =.  
  
- **excludeEMF** 0x04 dışlar EMF (geliştirilmiş meta dosyası) dosyaları =.  
  
- **excludeWMF** 0x08 dışlar WMF (Windows Meta dosyası) dosyaları =.  
  
- **excludeJPEG** 0x10 dışlar JPEG dosyaları =.  
  
- **excludePNG** 0x20 dışlar PNG dosyaları =.  
  
- **excludeTIFF** 0x40 dışlar TIFF dosyaları =.  
  
- **excludeIcon** 0x80 dışlar ICO (Windows simgesi) dosyaları =.  
  
- **excludeOther** = 0x80000000 Yukarıda listelenmeyen başka bir dosya türü dışlar.  
  
- **excludeDefaultLoad** = 0 yük, tüm dosya türleri varsayılan olarak dahil  
  
- **excludeDefaultSave** = **excludeIcon &#124; excludeEMF &#124; excludeWMF** genellikle sahip oldukları özel gereksinimler için kaydetme için bu dosyalar varsayılan olarak dışarıda bırakılır.  
  
 `chSeparator`  
 Görüntü biçimleri arasında kullanılan ayırıcı. Bkz: **açıklamalar** daha fazla bilgi için.  
  
### <a name="remarks"></a>Açıklamalar  
 MFC ile elde edilen biçim dizesi geçirebilirsiniz [CFileDialog](../../mfc/reference/cfiledialog-class.md) kullanılabilir görüntünün dosya uzantılarını kullanıma sunmak için nesne biçimleri **Dosya Aç** iletişim kutusu.  
  
 Parametre *strImporter* biçime sahiptir:  
  
 description0 dosya&#124;\*.ext0&#124;filedescription1&#124;\*.ext1&#124;.. .file açıklama *n*&#124;\*.Ext .ext *n*&#124;&#124;  
  
 Burada '&#124;' ayırıcı karakteri tarafından belirtilen `chSeparator`. Örneğin:  
  
 `"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`  
  
 Varsayılan ayırıcı kullan '&#124;' Bu dize bir MFC geçirirseniz `CFileDialog` nesnesi. Bu dize bir ortak geçirirseniz null ayırıcı '\0' kullanmak **Dosya Aç** iletişim kutusu.  
  
##  <a name="getmaxcolortableentries"></a>  CImage::GetMaxColorTableEntries  
 Renk tablosunda giriş sayısı üst sınırı alır.  
  
```
int GetMaxColorTableEntries() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Renk tablosundaki girişleri sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem yalnızca DIB bölüm bit eşlemler destekler.  
  
##  <a name="getpitch"></a>  CImage::GetPitch  
 Görüntüyü aralığını alır.  
  
```
int GetPitch() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Görüntü sıklığı. Dönüş değeri negatifse, bit eşlem aşağıdan yukarıya DIB ve kendi başlangıç sol alt köşesinde. Dönüş değeri pozitif ise, bit eşlem yukarıdan aşağıya DIB ve kendi başlangıç sol üst köşedeki.  
  
### <a name="remarks"></a>Açıklamalar  
 Aralık bayt cinsinden temsil eden bir bit eşlem satırın başına iki bellek adresi sonraki bit eşlem satır başlangıcı arasındaki uzaklığı ' dir. Aralık bayt cinsinden ölçülür olduğundan, görüntü aralık piksel biçimini belirlemek için yardımcı olur. Aralık için bit eşlemde ayrılan ek bellek de içerir.  
  
 Kullanım `GetPitch` ile [GetBits](#getbits) tek tek piksel görüntü bulunamadı.  
  
> [!NOTE]
>  Bu yöntem yalnızca DIB bölüm bit eşlemler destekler.  
  
##  <a name="getpixel"></a>  CImage::GetPixel  
 Tarafından belirtilen konumda piksel rengi alır *x* ve *y*.  
  
```
COLORREF GetPixel(int x,int y) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 X koordinatını piksel.  
  
 *Y*  
 Y koordinatını piksel.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kırmızı, yeşil, mavi (RGB) değeri piksel. Piksel geçerli kırpma bölgesinin dışındaki dönüş değeri ise, **CLR_INVALID**.  
  
##  <a name="getpixeladdress"></a>  CImage::GetPixelAddress  
 Bir piksel tam adresini alır.  
  
```
void* GetPixelAddress(int x,int y) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 X koordinatını piksel.  
  
 *Y*  
 Y koordinatını piksel.  
  
### <a name="remarks"></a>Açıklamalar  
 Adres piksel koordinatlarını, bit eşlem ve bit / piksel aralığını göre belirlenir.  
  
 Değerden 8 bit / piksel olan biçimleri, bu yöntem piksel içeren bayt adresini döndürür. Örneğin, resim biçimi 4 bit / piksel, varsa `GetPixelAddress` gerekir bayt ve ilk piksel adresini döndürür hesaplamak için bayt başına 2 piksel.  
  
> [!NOTE]
>  Bu yöntem yalnızca DIB bölüm bit eşlemler destekler.  
  
##  <a name="gettransparentcolor"></a>  CImage::GetTransparentColor  
 Saydam Rengi renk paletindeki dizinli konumunu alır.  
  
```
LONG GetTransparentColor() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Saydam Rengi dizini.  
  
##  <a name="getwidth"></a>  CImage::GetWidth  
 Görüntünün piksel cinsinden genişliği alır.  
  
```
int GetWidth() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bit eşlem piksel cinsinden genişliği.  
  
##  <a name="isdibsection"></a>  CImage::IsDIBSection  
 Ekli bit eşlem DIB bölüm olup olmadığını belirler.  
  
```
bool IsDIBSection() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** ekli bit eşlem DIB bölüm ise. Aksi takdirde **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bit eşlem DIB bölüm değilse, aşağıdaki kullanamazsınız `CImage` yalnızca DIB bölüm bit eşlemler destek yöntemleri:  
  
- [GetBits](#getbits)  
  
- [GetColorTable](#getcolortable)  
  
- [GetMaxColorTableEntries](#getmaxcolortableentries)  
  
- [GetPitch](#getpitch)  
  
- [GetPixelAddress](#getpixeladdress)  
  
- [IsIndexed](#isindexed)  
  
- [SetColorTable](#setcolortable)  
  
##  <a name="isindexed"></a>  CImage::IsIndexed  
 Bit eşlem 's piksel bir renk paleti eşlenen olup olmadığını belirler.  
  
```
bool IsIndexed() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** dizinli; Aksi takdirde **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem **doğru** yalnızca bit eşlem 8 bit ise (256 renk) veya daha az.  
  
> [!NOTE]
>  Bu yöntem yalnızca DIB bölüm bit eşlemler destekler.  
  
##  <a name="isnull"></a>  CImage::IsNull  
 Bir bit eşlem şu anda yüklü belirler.  
  
```
bool IsNull() const throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem **True** bir bit eşlem şu anda değilse yüklenen; Aksi takdirde **False**.  
  
##  <a name="istransparencysupported"></a>  CImage::IsTransparencySupported  
 Uygulama saydam bit eşlemler destekleyip desteklemediğini belirtir.  
  
```
static BOOL IsTransparencySupported() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli platform saydamlık destekliyorsa sıfır olmayan. Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değeri sıfır olmayan ise ve saydamlık desteklenir, çağrı [AlphaBlend](#alphablend), [TransparentBlt](#transparentblt), veya [çizin](#draw) saydam renkleri işleyecek.  
  

##  <a name="load"></a>  CImage::Load  
 Görüntüyü yükler.  
  
```
HRESULT Load(LPCTSTR pszFileName) throw();
HRESULT Load(IStream* pStream) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pszFileName`  
 Yüklemek için görüntü dosyasının adını içeren bir dize için bir işaretçi.  
  
 `pStream`  
 Yüklemek için görüntü dosyasının adını içeren bir akış için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen görüntü yükler *pszFileName* veya `pStream`.  
  
 Geçerli bir görüntü BMP, GIF, JPEG, PNG ve TIFF türleridir.  
  
##  <a name="loadfromresource"></a>  CImage::LoadFromResource  
 Bir görüntüden yüklediğinde bir `BITMAP` kaynak.  
  
```
void LoadFromResource(
 HINSTANCE hInstance,
 LPCTSTR pszResourceName) throw();

void LoadFromResource(
 HINSTANCE hInstance,
 UINT nIDResource) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `hInstance`  
 Görüntünün yüklenmesi içeren modülü örneğine işleyin.  
  
 `pszResourceName`  
 Yüklemek için görüntüyü içeren kaynak adını içeren dize için bir işaretçi.  
  
 `nIDResource`  
 Yüklemek için kaynak kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Kaynak türü olmalıdır `BITMAP`.  
  
##  <a name="maskblt"></a>  CImage::MaskBlt  
 Belirtilen maske ve Tarama işlemi kullanarak kaynak ve hedef bit eşlemler renk verilerini bir araya getirir.  
  
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
 `hDestDC`  
 Kaynağı olan yürütülebilir dosya içeren modülü için tanıtıcı.  
  
 `xDest`  
 X koordinatını, mantıksal birimlerini, hedef dikdörtgenin sol üst köşesinin.  
  
 `yDest`  
 Y koordinatını, mantıksal birimlerini, hedef dikdörtgenin sol üst köşesinin.  
  
 `nDestWidth`  
 Mantıksal birimlerini, hedef ve kaynak dikdörtgen bit eşlem genişliği.  
  
 `nDestHeight`  
 Hedef ve kaynak dikdörtgen bit eşlem mantıksal birimler yüksekliği.  
  
 `xSrc`  
 Kaynak eşlem sol üst köşesinin mantıksal x-koordinatı.  
  
 `ySrc`  
 Mantıksal y koordinatını kaynak bitmap sol üst köşesinin.  
  
 `hbmMask`  
 Kaynak cihaz bağlamı renk eşleminde birlikte tek renkli maskesi bit eşlem için işleyin.  
  
 `xMask`  
 Yatay piksel uzaklık tarafından belirtilen maskesi bit eşlem `hbmMask` parametresi.  
  
 `yMask`  
 Tarafından belirtilen maskesi bit eşlem için dikey piksel uzaklık `hbmMask` parametresi.  
  
 `dwROP`  
 Ön ve arka plan Üçlü tarama işlemi yöntemi kaynak ve hedef veri birleşimi denetlemek için kullandığı kodlarını belirtir. Arka plan tarama işlem kodu, bu değer yüksek düzey Word'ün yüksek düzey bayt depolanır; ön plan tarama işlem kodu, bu değer yüksek düzey Word'ün düşük düzey bayt depolanır; düşük düzey Word'ün bu değer yoksayılır ve sıfır olmalıdır. Ön plan ve arka plan bağlamında bu yöntemin bir tartışma için bkz: `MaskBlt` Windows SDK. Ortak tarama işlemi kodlarının listesi için bkz: `BitBlt` Windows SDK.  
  
 `rectDest`  
 Bir başvuru bir `RECT` yapısı, hedef belirleme.  
  
 `pointSrc`  
 A `POINT` kaynak dikdörtgenin sol üst köşesinin belirten yapısı.  
  
 `pointMask`  
 A **noktası** maskesi bit eşlem sol üst köşesinin belirten yapısı.  
  
 `pointDest`  
 Bir başvuru bir **noktası** hedef dikdörtgende mantıksal birimler sol üst köşesinin tanımlayan yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, sıfır olmayan Aksi halde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem Windows NT 4.0 ve üzeri sürümler için geçerlidir.  
  
##  <a name="operator_hbitmap"></a>  CImage::operator HBITMAP  
 Ekli Windows GDI işleyicisini almak için bu işleci kullanın `CImage` nesnesi. Bu işleç doğrudan kullanımını destekleyen bir atama işleci olan bir `HBITMAP` nesnesi.  
  
##  <a name="plgblt"></a>  CImage::PlgBlt  
 Bit bloğu aktarımı bir paralel kenarı bir hedef cihaz bağlamda içine dikdörtgenden kaynak aygıt bağlamda gerçekleştirir.  
  
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
 `hDestDC`  
 Hedef cihaz bağlamı için bir tanıtıcı.  
  
 *pPoints*  
 Hedef paralel kenarı üç köşelerinde tanımlayan üç mantıksal alan noktaları dizisi için bir işaretçi. Kaynak dikdörtgenin sol üst köşesinin bu dizi, bu diziye ikinci noktaya sağ üst köşesinde ve üçüncü noktası sol alt köşesine ilk noktanın eşleştirilir. Kaynak dikdörtgen sağ alt köşesindeki paralel kenarı örtük dördüncü noktaya eşlenir.  
  
 `hbmMask`  
 Kaynak dikdörtgen renkleri maskelemek için kullanılan isteğe bağlı bir tek renkli bitmap için bir tanıtıcı.  
  
 `xSrc`  
 X koordinatını, kaynak dikdörtgenin sol üst köşesinin, mantıksal birimler.  
  
 `ySrc`  
 Y koordinatını, kaynak dikdörtgenin sol üst köşesinin, mantıksal birimler.  
  
 `nSrcWidth`  
 Mantıksal birimleri, kaynak dikdörtgenin genişliği.  
  
 `nSrcHeight`  
 Kaynak dikdörtgenin mantıksal birimler yüksekliği.  
  
 `xMask`  
 Tek renkli bitmap sol üst köşesinin x-koordinatı.  
  
 `yMask`  
 Y koordinatını tek renkli bitmap sol üst köşesinin.  
  
 `rectSrc`  
 Bir başvuru bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı kaynak dikdörtgen koordinatlarını belirtme.  
  
 `pointMask`  
 A [noktası](http://msdn.microsoft.com/library/windows/desktop/dd162805) maskesi bit eşlem sol üst köşesinin belirten yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, sıfır olmayan Aksi halde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `hbmMask` geçerli bir tek renkli bitmap tanımlayan **PlgBit** bu bit eşlemi Kaynak dikdörtgen renk verilerini BITS maskelemek için kullanır.  
  
 Bu yöntem Windows NT 4.0 ve üzeri sürümler için geçerlidir. Bkz: [PlgBlt](http://msdn.microsoft.com/library/windows/desktop/dd162804) daha ayrıntılı bilgi için Windows SDK'sındaki.  
  
##  <a name="releasedc"></a>  CImage::ReleaseDC  
 Cihaz bağlamı serbest bırakır.  
  
```
void ReleaseDC() const throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir cihaz bağlamına aynı anda yalnızca bir bit eşlem seçilebilir çünkü çağırmalısınız `ReleaseDC` her çağrı için [GetDC](#getdc).  
  
##  <a name="releasegdiplus"></a>  CImage::ReleaseGDIPlus  
 GDI + tarafından kullanılan kaynakları serbest bırakır.  
  
```
void ReleaseGDIPlus() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Genel tarafından ayrılan kaynakları serbest bırakmak için bu yöntem çağrılmalıdır `CImage` nesnesi. Bkz: [CImage::CImage](#cimage).  
  
##  <a name="save"></a>  CImage::Save  
 Görüntüyü belirtilen akış veya disk üzerindeki bir dosyaya kaydeder.  
  
```
HRESULT Save(IStream* pStream,
 REFGUID guidFileType) const throw();

HRESULT Save(LPCTSTR pszFileName,
 REFGUID guidFileType= GUID_NULL) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pStream`  
 Dosya resim verileri içeren bir COM IStream nesnesi için bir işaretçi.  
  
 *pszFileName*  
 Görüntüsü için dosya adı için bir işaretçi.  
  
 `guidFileType`  
 Resim olarak kaydetmek için dosya türü. Aşağıdakilerden biri olabilir:  
  
- **ImageFormatBMP** sıkıştırılmamış bit eşlem resim.  
  
- **ImageFormatPNG** A Taşınabilir Ağ Grafik (PNG) sıkıştırılmış görüntü.  
  
- **ImageFormatJPEG** sıkıştırılmış bir JPEG Resim.  
  
- **ImageFormatGIF** sıkıştırılmış bir GIF resim.  
  
> [!NOTE]
>  Sabitler tam bir listesi için bkz: **görüntü dosya biçimi sabitleri** Windows SDK'sındaki.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen ad ve tür kullanarak görüntüsünü kaydetmek için bu işlevini çağırın. Varsa `guidFileType` parametresi dahil değildir, dosya adı dosya uzantısı görüntü biçimi belirlemek için kullanılır. Hiçbir uzantı sağlanırsa, görüntü BMP biçiminde kaydedilir.  
  
##  <a name="setcolortable"></a>  CImage::SetColorTable  
 Kırmızı, yeşil, mavi (RGB) renk değerleri girdi aralığı DIB bölümünün palette ayarlar.  
  
```
void SetColorTable(
  UINT iFirstColor, 
  UINT nColors,
  const RGBQUAD* prgbColors) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `iFirstColor`  
 İlk giriş ayarlamak için renk tablo dizini.  
  
 `nColors`  
 Ayarlamak için renk tablosu girdileri sayısı.  
  
 `prgbColors`  
 Dizi için bir işaretçi [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) rengini ayarlamak için yapıları tablo girişleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem yalnızca DIB bölüm bit eşlemler destekler.  
  
##  <a name="setpixel"></a>  CImage::SetPixel  
 Bit eşlemde belirli bir konumda bir piksel rengini ayarlar.  
  
```
void SetPixel(int x, int y, COLORREF color) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 Piksel ayarlamak için yatay konumu.  
  
 *Y*  
 Piksel ayarlamak için dikey konumu.  
  
 `color`  
 Piksel ayarladığınız rengi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kalan seçili kırpma bölgesinin dışındaki piksel koordinatları, bu yöntem başarısız olur.  
  
##  <a name="setpixelindexed"></a>  CImage::SetPixelIndexed  
 Konumunda bulunan renge piksel rengini ayarlar `iIndex` renk paletindeki.  
  
```
void SetPixelIndexed(int x, int y, int iIndex) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 Piksel ayarlamak için yatay konumu.  
  
 *Y*  
 Piksel ayarlamak için dikey konumu.  
  
 `iIndex`  
 Bir renk renk paletindeki dizini.  
  
##  <a name="setpixelrgb"></a>  CImage::SetPixelRGB  
 Tarafından belirlenen konumlara piksel ayarlar *x* ve *y* tarafından gösterilen renkleri için *r*, *g*, ve *b*, yeşil bir kırmızı, mavi (RGB) görüntüsü.  
  
```
void SetPixelRGB(  
 int x,
 int y,
 BYTE r,
 BYTE g,
 BYTE b) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 Piksel ayarlamak için yatay konumu.  
  
 *Y*  
 Piksel ayarlamak için dikey konumu.  
  
 *r*  
 Kırmızı renk yoğunluğu.  
  
 *g*  
 Yeşil renk yoğunluğu.  
  
 *b*  
 Mavi renkle yoğunluğu.  
  
### <a name="remarks"></a>Açıklamalar  
 Kırmızı, yeşil ve mavi parametreleri her 0 ile 255 arasında bir sayı ile temsil edilir. Tüm üç parametre sıfır olarak ayarlayarak, birleştirilmiş elde edilen rengi siyah olur. Tüm üç parametre 255 ayarlarsanız, birleştirilmiş elde edilen rengi beyaz.  
  
##  <a name="settransparentcolor"></a>  CImage::SetTransparentColor  
 Saydam olarak verilen bir dizinlenmiş konumda bir rengini belirler.  
  
```
LONG SetTransparentColor(LONG iTransparentColor) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *iTransparentColor*  
 Bir renk paletini çok saydam ayarlamak için renk dizini. -1, renk saydam olarak ayarlıdır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Renk dizinini önceden saydam olarak ayarlayın.  
  
##  <a name="stretchblt"></a>  CImage::StretchBlt  
 Bir bit eşlem kaynak aygıt bağlamından geçerli bu cihaz bağlamı kopyalar.  
  
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
 `hDestDC`  
 Hedef cihaz bağlamı için bir tanıtıcı.  
  
 `xDest`  
 X koordinatını, mantıksal birimlerini, hedef dikdörtgenin sol üst köşesinin.  
  
 `yDest`  
 Y koordinatını, mantıksal birimlerini, hedef dikdörtgenin sol üst köşesinin.  
  
 `nDestWidth`  
 Mantıksal birimleri, hedef dikdörtgenin genişliği.  
  
 `nDestHeight`  
 Hedef dikdörtgenin mantıksal birimler yüksekliği.  
  
 `dwROP`  
 Gerçekleştirilecek tarama işlemi. Tarama işlemi kodları kaynak, hedef ve desen BITS (şu anda seçili fırça tarafından tanımlandığı gibi) hedef oluşturmak için tam olarak nasıl birleştirileceğini tanımlar. Bkz: [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) diğer tarama işlemi kodları ve açıklamaları listesi için Windows SDK.  
  
 `rectDest`  
 Bir başvuru bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı, hedef belirleme.  
  
 `xSrc`  
 X koordinatını, kaynak dikdörtgenin sol üst köşesinin, mantıksal birimler.  
  
 `ySrc`  
 Y koordinatını, kaynak dikdörtgenin sol üst köşesinin, mantıksal birimler.  
  
 `nSrcWidth`  
 Mantıksal birimleri, kaynak dikdörtgenin genişliği.  
  
 `nSrcHeight`  
 Kaynak dikdörtgenin mantıksal birimler yüksekliği.  
  
 `rectSrc`  
 Bir başvuru bir `RECT` kaynağını tanımlayan yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, sıfır olmayan Aksi halde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [StretchBlt](http://msdn.microsoft.com/library/windows/desktop/dd145120) Windows SDK'sındaki.  
  
##  <a name="transparentblt"></a>  CImage::TransparentBlt  
 Bir bit eşlem kaynak aygıt bağlamından geçerli bu cihaz bağlamı kopyalar.  
  
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
 `hDestDC`  
 Hedef cihaz bağlamı için bir tanıtıcı.  
  
 `xDest`  
 X koordinatını, mantıksal birimlerini, hedef dikdörtgenin sol üst köşesinin.  
  
 `yDest`  
 Y koordinatını, mantıksal birimlerini, hedef dikdörtgenin sol üst köşesinin.  
  
 `nDestWidth`  
 Mantıksal birimleri, hedef dikdörtgenin genişliği.  
  
 `nDestHeight`  
 Hedef dikdörtgenin mantıksal birimler yüksekliği.  
  
 *crTransparent*  
 Saydam olarak işlemek için kaynak bitmap rengi. Varsayılan olarak, **CLR_INVALID**, resminin saydam rengi ayarlanmış renk kullanılması gerektiğini belirten.  
  
 `rectDest`  
 Bir başvuru bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı, hedef belirleme.  
  
 `xSrc`  
 X koordinatını, kaynak dikdörtgenin sol üst köşesinin, mantıksal birimler.  
  
 `ySrc`  
 Y koordinatını, kaynak dikdörtgenin sol üst köşesinin, mantıksal birimler.  
  
 `nSrcWidth`  
 Mantıksal birimleri, kaynak dikdörtgenin genişliği.  
  
 `nSrcHeight`  
 Kaynak dikdörtgenin mantıksal birimler yüksekliği.  
  
 `rectSrc`  
 Bir başvuru bir `RECT` kaynağını tanımlayan yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** başarılı olursa, aksi takdirde **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 `TransparentBlt` Kaynak bit eşlemler 4 bit / piksel ve 8 bit / piksel için desteklenir. Kullanım [CImage::AlphaBlend](#alphablend) saydamlığı olan 32 bit-piksel başına bit eşlemler belirtmek için.  
  
  
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
 [MMXSwarm örnek](../../visual-cpp-samples.md)   
 [SimpleImage örnek](../../visual-cpp-samples.md)   
 [CİHAZDAN bağımsız bit eşlemler](http://msdn.microsoft.com/library/windows/desktop/dd183562)   
 [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183494)   
 [ATL COM Masaüstü bileşenleri](../../atl/atl-com-desktop-components.md) [CİHAZDAN bağımsız bit eşlemler](http://msdn.microsoft.com/library/windows/desktop/dd183562)   
 [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183494)   









