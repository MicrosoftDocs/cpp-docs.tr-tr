---
title: CPalette sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPalette
- AFXWIN/CPalette
- AFXWIN/CPalette::CPalette
- AFXWIN/CPalette::AnimatePalette
- AFXWIN/CPalette::CreateHalftonePalette
- AFXWIN/CPalette::CreatePalette
- AFXWIN/CPalette::FromHandle
- AFXWIN/CPalette::GetEntryCount
- AFXWIN/CPalette::GetNearestPaletteIndex
- AFXWIN/CPalette::GetPaletteEntries
- AFXWIN/CPalette::ResizePalette
- AFXWIN/CPalette::SetPaletteEntries
dev_langs:
- C++
helpviewer_keywords:
- CPalette [MFC], CPalette
- CPalette [MFC], AnimatePalette
- CPalette [MFC], CreateHalftonePalette
- CPalette [MFC], CreatePalette
- CPalette [MFC], FromHandle
- CPalette [MFC], GetEntryCount
- CPalette [MFC], GetNearestPaletteIndex
- CPalette [MFC], GetPaletteEntries
- CPalette [MFC], ResizePalette
- CPalette [MFC], SetPaletteEntries
ms.assetid: 8cd95498-53ed-4852-85e1-70e522541114
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb5aeef3970488c293d4199261d765f2531c201a
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079687"
---
# <a name="cpalette-class"></a>CPalette sınıfı
Bir Windows renk paleti yalıtır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CPalette : public CGdiObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPalette::CPalette](#cpalette)|Oluşturan bir `CPalette` ekli Windows palet nesnesiyle. Başlatması gerekir `CPalette` kullanılabilmesi için önce başlatma üye işlevleri biriyle nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPalette::AnimatePalette](#animatepalette)|Tarafından tanımlanan mantıksal paletindeki girişleri değiştirir `CPalette` nesnesi. Windows Sistem paleti içine yeni girişler hemen eşlendiğinden kendi istemci alanını güncelleştirmek uygulama yok.|  
|[CPalette::CreateHalftonePalette](#createhalftonepalette)|Cihaz bağlamı için bir noktalı paleti oluşturur ve ona ekler `CPalette` nesnesi.|  
|[CPalette::CreatePalette](#createpalette)|Bir Windows renk paleti oluşturur ve ona ekler `CPalette` nesnesi.|  
|[CPalette::FromHandle](#fromhandle)|Bir işaretçi döndüren bir `CPalette` nesnesi tanıtıcı bir Windows palet nesnesine verildiğinde.|  
|[CPalette::GetEntryCount](#getentrycount)|Mantıksal paletindeki paleti girdileri sayısını alır.|  
|[CPalette::GetNearestPaletteIndex](#getnearestpaletteindex)|Bir renk değeri en yakından eşleşen mantıksal palette giriş dizinini döndürür.|  
|[CPalette::GetPaletteEntries](#getpaletteentries)|Mantıksal paletindeki paleti girdileri aralığını alır.|  
|[CPalette::ResizePalette](#resizepalette)|Tarafından belirtilen mantıksal palet boyutunu değiştirir `CPalette` belirtilen sayısı giriş nesnesi.|  
|[CPalette::SetPaletteEntries](#setpaletteentries)|RGB renk değerleri ve bayrakları mantıksal paleti girdileri çeşitli ayarlar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPalette::operator HPALETTE](#operator_hpalette)|Döndürür `HPALETTE` bağlı `CPalette`.|  
  
## <a name="remarks"></a>Açıklamalar  
 Palet bir uygulama ile (örneğin, bir görüntü aygıtı) bir renk çıktı aygıtı arasında bir arabirim sağlar. Arabirim diğer uygulamalar tarafından görüntülenen renk ciddi bir şekilde müdahale olmadan çıktı aygıtının renk özelliklerinden tam anlamıyla yararlanabilmek için uygulamayı sağlar. Windows, kullanılan renkleri belirlemek için uygulamanın mantıksal palet (gerekli renk listesi) ve (hangi kullanılabilir renk tanımlar) sistem paleti kullanır.  
  
 A `CPalette` nesne paleti düzenleme nesne tarafından başvuruda bulunulan üye işlevleri sağlar. Oluşturmak bir `CPalette` nesne ve üye işlevleri gerçek palet, bir grafik cihaz arabirimi (GDI) nesnesi oluşturmak ve girdilerini ve diğer özellikleri değiştirmek için kullanın.  
  
 Kullanma hakkında daha fazla bilgi için `CPalette`, bkz: [grafik nesneleri](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPalette`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="animatepalette"></a>  CPalette::AnimatePalette  
 Bağlı mantıksal paletindeki girişleri değiştirir `CPalette` nesnesi.  
  
```  
void AnimatePalette(
    UINT nStartIndex,  
    UINT nNumEntries,  
    LPPALETTEENTRY lpPaletteColors);
```  
  
### <a name="parameters"></a>Parametreler  
 *nStartIndex*  
 İlk giriş animasyon için palette belirtir.  
  
 *nNumEntries*  
 Animasyon için palette girdisi sayısını belirtir.  
  
 *lpPaletteColors*  
 İşaret eden bir dizi ilk üye için [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) tarafından tanımlanan paleti girdileri değiştirmek için yapıları *nStartIndex* ve *nNumEntries*.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir uygulama çağırdığında `AnimatePalette`, Windows Sistem paleti içine yeni girişler hemen eşlendiğinden kendi istemci alanını güncelleştirmek yok.  
  
 `AnimatePalette` İşlevi yalnızca girişlerle değiştirme **PC_RESERVED** bayrağı ayarlanmış karşılık gelen **palPaletteEntry** üyesi [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) yapısı için eklenen `CPalette` nesnesi. Bkz: **LOGPALETTE** bu yapısı hakkında daha fazla bilgi için Windows SDK'sındaki.  
  
##  <a name="cpalette"></a>  CPalette::CPalette  
 Oluşturan bir `CPalette` nesnesi.  
  
```  
CPalette();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmanız kadar nesnenin ekli palet sahip `CreatePalette` bir eklemek için.  
  
##  <a name="createhalftonepalette"></a>  CPalette::CreateHalftonePalette  
 Cihaz bağlamı için bir noktalı paleti oluşturur.  
  
```  
BOOL CreateHalftonePalette(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 *pDC*  
 Cihaz bağlamı tanımlar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir cihaz bağlamı uzatma modu ayarlandığında bir uygulama noktalı palet oluşturmalısınız **noktalı**. Tarafından döndürülen mantıksal noktalı palet [CreateHalftonePalette](http://msdn.microsoft.com/library/windows/desktop/dd183503) üye işlevi sonra seçili ve gerekir önce cihaz bağlamı içinde gerçekleşen [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) veya [ StretchDIBits](http://msdn.microsoft.com/library/windows/desktop/dd145121) işlevi çağrılır.  
  
 Daha fazla bilgi için Windows SDK'sı gördükleri hakkında `CreateHalftonePalette` ve **StretchDIBits**.  
  
##  <a name="createpalette"></a>  CPalette::CreatePalette  
 Başlatır bir `CPalette` Windows mantıksal renk paletini oluşturarak ve eklemeyi nesne `CPalette` nesne.  
  
```  
BOOL CreatePalette(LPLOGPALETTE lpLogPalette);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpLogPalette*  
 İşaret eden bir [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) mantıksal palet renkleri hakkında bilgi içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için Windows SDK'sı gördükleri hakkında **LOGPALETTE** yapısı.  
  
##  <a name="fromhandle"></a>  CPalette::FromHandle  
 Bir işaretçi döndüren bir `CPalette` nesnesi tanıtıcı bir Windows palet nesnesine verildiğinde.  
  
```  
static CPalette* PASCAL FromHandle(HPALETTE hPalette);
```  
  
### <a name="parameters"></a>Parametreler  
 *hPalette*  
 Bir Windows GDI renk paleti için bir tanıtıcı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CPalette` nesne başarılı; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa bir `CPalette` nesne zaten iliştirilmemiş Windows palet geçici bir `CPalette` nesnesi oluşturulur ve bağlı. Bu geçici `CPalette` nesnesi, hangi tüm geçici grafiği zaman durdurulacağını sonraki açışınızda uygulama boşta kalma süresi, olay döngüde olana kadar nesneler silinir yalnızca geçerli. Diğer bir deyişle, yalnızca bir pencere ileti işleme sırasında geçici nesne geçerli değil.  
  
##  <a name="getentrycount"></a>  CPalette::GetEntryCount  
 Belirli bir mantıksal paleti girdileri sayısını almak üzere bu üye işlevini çağırın.  
  
```  
int GetEntryCount();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir mantıksal paleti girdileri sayısı.  
  
##  <a name="getnearestpaletteindex"></a>  CPalette::GetNearestPaletteIndex  
 Belirtilen renk değeri en yakından eşleşen mantıksal palette giriş dizinini döndürür.  
  
```  
UINT GetNearestPaletteIndex(COLORREF crColor) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *crColor*  
 Eşleştirilecek rengini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Mantıksal paletindeki bir giriş dizini. Giriş en neredeyse belirtilen renk eşleşen renk içerir.  
  
##  <a name="getpaletteentries"></a>  CPalette::GetPaletteEntries  
 Mantıksal paletindeki paleti girdileri aralığını alır.  
  
```  
UINT GetPaletteEntries(
    UINT nStartIndex,  
    UINT nNumEntries,  
    LPPALETTEENTRY lpPaletteColors) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *nStartIndex*  
 İlk Giriş alınacak mantıksal palette belirtir.  
  
 *nNumEntries*  
 Alınacak mantıksal palette girdisi sayısını belirtir.  
  
 *lpPaletteColors*  
 Noktaları için bir dizi [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) paleti girdileri almak için veri yapıları. Dizi en az sayıda veri yapılarını tarafından belirtilen içermelidir *nNumEntries*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Girdi sayısı mantıksal paletinden alınır; 0 işlevi başarısız oldu.  
  
##  <a name="operator_hpalette"></a>  CPalette::operator HPALETTE  
 Ekli Windows GDI işleyicisini almak için bu işleci kullanın `CPalette` nesnesi.  
  
```  
operator HPALETTE() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı, Windows GDI nesnesi için bir tanıtıcı tarafından temsil edilen varsa `CPalette` nesne; Aksi halde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç doğrudan kullanımını destekleyen bir atama işleci olan bir `HPALETTE` nesnesi.  
  
 Grafik nesneleri kullanma hakkında daha fazla bilgi için bkz: [grafik nesneleri](http://msdn.microsoft.com/library/windows/desktop/dd144962) Windows SDK.  
  
##  <a name="resizepalette"></a>  CPalette::ResizePalette  
 Bağlı mantıksal palet boyutunu değiştirir `CPalette` nesne sayısı tarafından belirtilen giriş *nNumEntries*.  
  
```  
BOOL ResizePalette(UINT nNumEntries);
```  
  
### <a name="parameters"></a>Parametreler  
 *nNumEntries*  
 Bunu yeniden boyutlandırılmış sonra palette girdisi sayısını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Palet başarıyla boyutlandırıldı, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir uygulama çağırırsa `ResizePalette` palet boyutunu azaltmak için yeniden boyutlandırılmış palette kalan girişleri değiştirilmemiştir. Uygulama çağırırsa `ResizePalette` palet genişletmek için ek paleti girdileri siyah (kırmızı, yeşil ve mavi değerleri olan tüm 0) olarak ayarlanır ve tüm ek girdiler için bayraklar 0 olarak ayarlayın.  
  
 Windows API'si hakkında daha fazla bilgi için `ResizePalette`, bkz: [ResizePalette](http://msdn.microsoft.com/library/windows/desktop/dd162928) Windows SDK'sındaki.  
  
##  <a name="setpaletteentries"></a>  CPalette::SetPaletteEntries  
 RGB renk değerleri ve bayrakları mantıksal paleti girdileri çeşitli ayarlar.  
  
```  
UINT SetPaletteEntries(
    UINT nStartIndex,  
    UINT nNumEntries,  
    LPPALETTEENTRY lpPaletteColors);
```  
  
### <a name="parameters"></a>Parametreler  
 *nStartIndex*  
 İlk giriş ayarlanacak mantıksal palette belirtir.  
  
 *nNumEntries*  
 Girdi sayısı ayarlanacak mantıksal palette belirtir.  
  
 *lpPaletteColors*  
 Noktaları için bir dizi [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) paleti girdileri almak için veri yapıları. Dizi en az sayıda veri yapılarını tarafından belirtilen içermelidir *nNumEntries*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Girdi sayısı mantıksal palette ayarlayın; 0 işlevi başarısız oldu.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulama çağırdığında mantıksal palet bir cihaz bağlamına seçtiyseniz `SetPaletteEntries`, değişiklikler uygulamayı çağrıları kadar etkili olmaz [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette).  
  
 Windows yapısı hakkında daha fazla bilgi için **PALETTEENTRY**, bkz: [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) Windows SDK'sındaki.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek DIBLOOK](../../visual-cpp-samples.md)   
 [CGdiObject sınıfı](../../mfc/reference/cgdiobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CPalette::GetPaletteEntries](#getpaletteentries)   
 [CPalette::SetPaletteEntries](#setpaletteentries)



