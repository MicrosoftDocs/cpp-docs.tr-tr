---
title: CFont sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFont
- AFXWIN/CFont
- AFXWIN/CFont::CFont
- AFXWIN/CFont::CreateFont
- AFXWIN/CFont::CreateFontIndirect
- AFXWIN/CFont::CreatePointFont
- AFXWIN/CFont::CreatePointFontIndirect
- AFXWIN/CFont::FromHandle
- AFXWIN/CFont::GetLogFont
dev_langs:
- C++
helpviewer_keywords:
- CFont [MFC], CFont
- CFont [MFC], CreateFont
- CFont [MFC], CreateFontIndirect
- CFont [MFC], CreatePointFont
- CFont [MFC], CreatePointFontIndirect
- CFont [MFC], FromHandle
- CFont [MFC], GetLogFont
ms.assetid: 3fad6bfe-d6ce-4ab9-967a-5ce0aa102800
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c26cf70ad52037b4ebe88b983e6d9a91273897cf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369674"
---
# <a name="cfont-class"></a>CFont sınıfı
Bir Windows grafik cihaz arabirimi (GDI) yazı tipi yalıtır ve yazı tipi yönlendirmek için üye işlevleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CFont : public CGdiObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFont::CFont](#cfont)|Oluşturan bir `CFont` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFont::CreateFont](#createfont)|Başlatır bir `CFont` belirtilen özelliklere sahip.|  
|[CFont::CreateFontIndirect](#createfontindirect)|Başlatır bir `CFont` nesne verilen özelliklere sahip bir `LOGFONT` yapısı.|  
|[CFont::CreatePointFont](#createpointfont)|Başlatır bir `CFont` belirtilen yüksekliği ile ölçülen içinde onda noktasının ve yazı tipi.|  
|[CFont::CreatePointFontIndirect](#createpointfontindirect)|Aynı `CreateFontIndirect` dışında yazı tipi yükseklik onda mantıksal birimler yerine bir nokta ölçülür.|  
|[CFont::FromHandle](#fromhandle)|Bir işaretçi döndüren bir `CFont` nesnesi Windows verildiğinde **HFONT**.|  
|[CFont::GetLogFont](#getlogfont)|Doldurur bir `LOGFONT` bağlı mantıksal yazı tipi hakkında bilgi içeren `CFont` nesnesi.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFont::operator HFONT](#operator_hfont)|Windows GDI yazı tipi tanıtıcı iliştirilmiş döndürür `CFont` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanılacak bir `CFont` nesne, oluşturmak bir `CFont` nesne ve bir Windows yazı tipi ile ekleme [CreateFont](#createfont), [CreateFontIndirect](#createfontindirect), [CreatePointFont](#createpointfont), veya [CreatePointFontIndirect](#createpointfontindirect)ve ardından yazı tipini değiştirmek için nesnenin üye işlevleri kullanın.  
  
 `CreatePointFont` Ve `CreatePointFontIndirect` işlevleri daha kolay genellikle `CreateFont` veya `CreateFontIndirect` dönüştürme yüksekliği için yazı tipi noktası boyutlu bir mantıksal birimler otomatik olarak yaparlar beri.  
  
 Daha fazla bilgi için `CFont`, bkz: [grafik nesneleri](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CFont`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="cfont"></a>  CFont::CFont  
 Oluşturan bir `CFont` nesnesi.  
  
```  
CFont();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Sonuç nesnesi ile başlatılmalıdır `CreateFont`, `CreateFontIndirect`, `CreatePointFont`, veya `CreatePointFontIndirect` kullanılabilmesi için önce.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#70](../../mfc/codesnippet/cpp/cfont-class_1.cpp)]  
  
##  <a name="createfont"></a>  CFont::CreateFont  
 Başlatır bir `CFont` nesne belirtilen özelliklere sahip.  
  
```  
BOOL CreateFont(
    int nHeight,  
    int nWidth,  
    int nEscapement,  
    int nOrientation,  
    int nWeight,  
    BYTE bItalic,  
    BYTE bUnderline,  
    BYTE cStrikeOut,  
    BYTE nCharSet,  
    BYTE nOutPrecision,  
    BYTE nClipPrecision,  
    BYTE nQuality,  
    BYTE nPitchAndFamily,  
    LPCTSTR lpszFacename);
```  
  
### <a name="parameters"></a>Parametreler  
 `nHeight`  
 İstenen yüksekliğini (mantıksal birimleri) yazı tipini belirtir. Bkz: `lfHeight` üyesi [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)bir açıklama için Windows SDK'sı yapısında. Mutlak değerini `nHeight` dönüştürmeden sonra 16.384 aygıt birimleri aşmamalıdır. Tüm yazı tiplerini istenen boyutu aşarsa tüm yükseklik karşılaştırmaları için istenen boyuta aşmayan en büyük yazı tipini veya en küçük yazı tipi için yazı tipi Eşleyici arar.  
  
 `nWidth`  
 Ortalama genişliğini (mantıksal birimleri) karakterleri yazı tipini belirtir. Varsa `nWidth` 0'dır, aygıt en boy oranını fark mutlak değeri tarafından belirlenir yakın eşleşmeyi bulmak için yazı tiplerini digitization en boy oranını karşı eşleşti.  
  
 `nEscapement`  
 (0,1 derecelik birimlerindeki) escapement vektör ve görüntü yüzeyini x ekseni arasındaki açıyı belirtir. Escapement vektör satırındaki ilk ve son karakterler kaynakları aracılığıyla satırıdır. Açı saatin tersi yönde eksenindeki ölçülür. Bkz: `lfEscapement` üye `LOGFONT` daha fazla bilgi için Windows SDK'sı yapısında.  
  
 `nOrientation`  
 (0,1 derecelik birimlerindeki) temel bir karakterin x ekseni arasındaki açıyı belirtir. Açı saatin tersi yönde y yönünde aşağı ve y yönünde çalışır durumda koordinat sistemleri için x ekseni saat yönünde Döndürülmüş koordinat sistemleri için x ekseni ölçülür.  
  
 `nWeight`  
 (Kaynağa piksel cinsinden başına 1000) yazı tipini belirtir. Bkz: `lfWeight` üye `LOGFONT` daha fazla bilgi için Windows SDK'sı yapısında. Açıklanan yaklaşık değerlerdir; Gerçek görünümü üzerinde yazı tipi bağlıdır. Bazı yazı tipleri yalnızca sahip `FW_NORMAL`, `FW_REGULAR`, ve `FW_BOLD` ağırlıkları. Varsa `FW_DONTCARE` belirtilmemişse, varsayılan ağırlık kullanılır.  
  
 `bItalic`  
 Yazı tipi italik olup olmadığını belirtir.  
  
 `bUnderline`  
 Yazı tipinin altı çizili olup olmadığını belirtir.  
  
 `cStrikeOut`  
 Yazı tipi karakter harfi olup olmadığını belirtir. Üstü çizili yazı tipini belirtir sıfır olmayan bir değere ayarlayın.  
  
 `nCharSet`  
 Yazı tipinin karakter setSee belirtir `lfCharSet` üye `LOGFONT` değerleri listesi için Windows SDK'sı yapısında.  
  
 OEM karakter kümesi sistem bağımlıdır.  
  
 Yazı tipleri diğer karakter kümeleriyle sistemde mevcut. Bilinmeyen karakter kümesi ile bir yazı tipi kullanan bir uygulamayı Çevir veya bu yazı tipiyle işlenmek üzere olduğunuz dizeleri yorumlama kullanmamanız gerekir. Bunun yerine, dizeleri doğrudan çıkış aygıt sürücüsü geçirilmesi gerekir.  
  
 Yazı tipi Eşleyici kullanmayan `DEFAULT_CHARSET` değeri. Bir uygulama adı ve mantıksal yazı tipi tam olarak tanımlamak için bir yazı tipi boyutunu izin vermek için bu değeri kullanabilirsiniz. Belirtilen ada sahip bir yazıtipi yoksa, herhangi bir karakter kümesinden bir yazı tipi için belirtilen yazı tipi yerine. Beklenmeyen sonuçlardan kaçınmak için uygulamaların kullanması gereken `DEFAULT_CHARSET` tutumlu değeri.  
  
 `nOutPrecision`  
 İstenen çıkış duyarlık belirtir. Çıktı duyarlık çıkış istenen yazı tipinin yükseklik, genişlik, karakter yönü, escapement ve aralık ne kadar yakından eşleşmelidir tanımlar. Bkz: `lfOutPrecision` üye `LOGFONT` listesi değerleri ve daha fazla bilgi için Windows SDK'sı yapısında.  
  
 `nClipPrecision`  
 İstenen kırpma duyarlık belirtir. Kırpma duyarlık kısmen kırpma bölgesinin dışındaki karakterleri küçük nasıl tanımlar. Bkz: `lfClipPrecision` üye `LOGFONT` değerleri listesi için Windows SDK'sı yapısında.  
  
 Katıştırılmış bir salt okunur yazı tipini kullanmak için bir uygulama belirtilmesi gerekir `CLIP_ENCAPSULATE`.  
  
 Aygıt, TrueType ve vektör yazı tipleri tutarlı dönüşünü elde etmek için bir uygulama veya işlecini birleştirmek için kullanabilirsiniz `CLIP_LH_ANGLES` herhangi diğer bir değerle `nClipPrecision` değerleri. Varsa `CLIP_LH_ANGLES` bit ayarlanmışsa, tüm yazı tipleri için döndürme koordinat sistemi yönünü sol olmasına bağlıdır veya sağ. (Açıklamasını koordinat sistemleri yönünü hakkında daha fazla bilgi için bkz: `nOrientation` parametresi.) Varsa `CLIP_LH_ANGLES` olan ayarlanmadı, Aygıt yazı tiplerini her zaman döndürme saatin tersi yönde, ancak diğer yazı tiplerini dönüşünü koordinat sistemi yönünü bağlıdır.  
  
 `nQuality`  
 GDI olanlar gerçek fiziksel yazı tipi için yazı tipi mantıksal özniteliklerini eşleşecek şekilde nasıl dikkatle denemelidir tanımlar yazı tipinin çıktı kalitesini belirler. Bkz: `lfQuality` üye `LOGFONT` değerleri listesi için Windows SDK'sı yapısında.  
  
 `nPitchAndFamily`  
 Yazı tipi ailesi ve aralığı belirtir. Bkz: `lfPitchAndFamily` üye `LOGFONT` listesi değerleri ve daha fazla bilgi için Windows SDK'sı yapısında.  
  
 `lpszFacename`  
 A `CString` veya işaretçi null ile sonlandırılmış dizeye yazı tipini yazı tipi adını belirtir. Bu dize uzunluğu 30 karakterden uzun olamaz. Windows [EnumFontFamilies](http://msdn.microsoft.com/library/windows/desktop/dd162619) işlevi, şu anda kullanılabilir tüm yazı tipleri numaralandırmak için kullanılabilir. Varsa `lpszFacename` olan `NULL`, bir CİHAZDAN bağımsız yazı tipi GDI kullanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Yazı tipi daha sonra herhangi bir cihaz bağlamı için yazı tipi olarak seçilebilir.  
  
 `CreateFont` İşlevi yeni bir Windows GDI yazı tipi oluşturulamadı. Bunu yalnızca en yakın eşleşme kullanılabilir fiziksel yazı GDI seçer.  
  
 Uygulamaları mantıksal bir yazı tipi oluştururken, varsayılan ayarları çoğu parametrelerini kullanabilirsiniz. Her zaman belirli değerleri verilmelidir parametreler `nHeight` ve `lpszFacename`. Varsa `nHeight` ve `lpszFacename` ayarlı değil uygulama tarafından oluşturulan mantıksal yazı tipi aygıt bağlıdır.  
  
 İle tamamladığınızda `CFont` tarafından oluşturulan nesne `CreateFont` işlev, kullanın `CDC::SelectObject` cihaz bağlamına farklı bir yazı tipi seçmek için delete `CFont` artık gerekli nesne.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#71](../../mfc/codesnippet/cpp/cfont-class_2.cpp)]  
  
##  <a name="createfontindirect"></a>  CFont::CreateFontIndirect  
 Başlatır bir `CFont` nesne verilen özelliklere sahip bir [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)yapısı.  
  
```  
BOOL CreateFontIndirect(const LOGFONT* lpLogFont);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpLogFont`  
 İşaret eden bir `LOGFONT` mantıksal yazı tipi özelliklerini tanımlayan yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Yazı tipi, geçerli yazı tipi herhangi bir cihaz için sonradan seçilebilir.  
  
 Bu yazı tipini belirtilen özelliklere sahip [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) yapısı. Yazı tipi seçildiğinde kullanarak [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) üye işlevi GDI yazı tipi Eşleyici mantıksal yazı tipi varolan fiziksel yazı tipi ile eşleşecek şekilde çalışır. Mantıksal yazı tipi için tam bir eşleşme bulmak yazı tipi Eşleyici başarısız olursa, kadar çok istenen özelliklerden mümkün olduğunca özelliklerini eşleşen alternatif bir yazı tipi sağlar.  
  
 Artık gerektiğinde `CFont` tarafından oluşturulan nesne `CreateFontIndirect` işlev, kullanın `CDC::SelectObject` cihaz bağlamına farklı bir yazı tipi seçmek için delete `CFont` artık gerekli nesne.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#72](../../mfc/codesnippet/cpp/cfont-class_3.cpp)]  
  
##  <a name="createpointfont"></a>  CFont::CreatePointFont  
 Bu işlev bir yazı tipini belirtilen yazı tipi oluşturmak ve nokta boyutu için basit bir yol sağlar.  
  
```  
BOOL CreatePointFont(
    int nPointSize,  
    LPCTSTR lpszFaceName,  
    CDC* pDC = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `nPointSize`  
 Yazı tipi yüksekliği noktasının onda istedi. (Örneğin, 12 noktası yazı tipi istemek için 120 geçirin.)  
  
 `lpszFaceName`  
 A `CString` veya işaretçi null ile sonlandırılmış dizeye yazı tipini yazı tipi adını belirtir. Bu dize uzunluğu 30 karakterden uzun olamaz. Windows **EnumFontFamilies** işlevi, şu anda kullanılabilir tüm yazı tipleri numaralandırmak için kullanılabilir. Varsa `lpszFaceName` olan **NULL**, bir CİHAZDAN bağımsız yazı tipi GDI kullanır.  
  
 `pDC`  
 İşaretçi [CDC](../../mfc/reference/cdc-class.md) yüksekliği dönüştürmek için kullanılacak nesne `nPointSize` mantıksal birimler için. Varsa **NULL**, ekran cihaz bağlamı dönüştürme için kullanılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, sıfır olmayan Aksi halde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Yükseklik otomatik olarak dönüştürür `nPointSize` kullanarak mantıksal birimler için `CDC` tarafından için nesne işaret `pDC`.  
  
 İle tamamladığınızda `CFont` tarafından oluşturulan nesne `CreatePointFont` işlev, önce cihaz bağlamı dışında yazı tipini seçin, ardından silin `CFont` nesnesi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#73](../../mfc/codesnippet/cpp/cfont-class_4.cpp)]  
  
##  <a name="createpointfontindirect"></a>  CFont::CreatePointFontIndirect  
 Bu işlev aynıdır [CreateFontIndirect](#createfontindirect) dışında **lfHeight** üyesi `LOGFONT` cihaz yerine noktası birimleri onda yorumlanır.  
  
```  
BOOL CreatePointFontIndirect(
    const LOGFONT* lpLogFont,  
    CDC* pDC = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpLogFont`  
 İşaret eden bir [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) mantıksal yazı tipi özelliklerini tanımlayan yapısı. **LfHeight** üyesi `LOGFONT` yapısı onda mantıksal birimler yerine bir nokta ölçülür. (Örneğin, ayarlamak **lfHeight** 12 noktası yazı tipi istemek için 120 için.)  
  
 `pDC`  
 İşaretçi [CDC](../../mfc/reference/cdc-class.md) yüksekliği dönüştürmek için kullanılacak nesne **lfHeight** mantıksal birimler için. Varsa **NULL**, ekran cihaz bağlamı dönüştürme için kullanılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, sıfır olmayan Aksi halde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev otomatik olarak yüksekliği dönüştürür **lfHeight** kullanarak mantıksal birimler için `CDC` tarafından için nesne işaret `pDC` geçirilmeden önce `LOGFONT` yapısı Windows açın.  
  
 İle tamamladığınızda `CFont` tarafından oluşturulan nesne `CreatePointFontIndirect` işlev, önce cihaz bağlamı dışında yazı tipini seçin, ardından silin `CFont` nesnesi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#74](../../mfc/codesnippet/cpp/cfont-class_5.cpp)]  
  
##  <a name="fromhandle"></a>  CFont::FromHandle  
 Bir işaretçi döndüren bir `CFont` nesne verildiğinde bir **HFONT** işlemek için bir Windows GDI yazı tipi nesnesi.  
  
```  
static CFont* PASCAL FromHandle(HFONT hFont);
```  
  
### <a name="parameters"></a>Parametreler  
 `hFont`  
 Bir **HFONT** işlemek için bir Windows yazı tipi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CFont` nesne başarılı; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa bir `CFont` nesne zaten iliştirilmemiş tanıtıcıyı, geçici bir `CFont` nesnesi oluşturulur ve bağlı. Bu geçici `CFont` nesnesi, hangi tüm geçici grafiği zaman durdurulacağını sonraki açışınızda uygulama boşta kalma süresi, olay döngüde olana kadar nesneler silinir yalnızca geçerli. Bu bildiren başka bir geçici nesne yalnızca bir pencere ileti işleme sırasında geçerli olduğunu yoludur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#75](../../mfc/codesnippet/cpp/cfont-class_6.cpp)]  
  
##  <a name="getlogfont"></a>  CFont::GetLogFont  
 Bir kopyasını almak için bu işlevi çağırmak `LOGFONT` için yapı `CFont`.  
  
```  
int GetLogFont(LOGFONT* pLogFont);
```  
  
### <a name="parameters"></a>Parametreler  
 *pLogFont*  
 İşaretçi [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) yazı tipi bilgilerini almak için yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa, aksi takdirde 0 sıfır olmayan.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#76](../../mfc/codesnippet/cpp/cfont-class_7.cpp)]  
  
##  <a name="operator_hfont"></a>  CFont::operator HFONT  
 Bağlı yazı tipinin Windows GDI işleme almak için bu işleci kullanın `CFont` nesnesi.  
  
```  
operator HFONT() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Windows GDI yazı tipi nesne tanıtıcısını bağlı `CFont` başarılı; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç dönüştürmeleri için otomatik olarak kullanıldığından `CFont` için [yazı tipleri ve metin](http://msdn.microsoft.com/library/windows/desktop/dd144819), geçirebilirsiniz `CFont` beklediğiniz işlevleri nesnelere **HFONT**s.  
  
 Grafik nesneleri kullanma hakkında daha fazla bilgi için bkz: [grafik nesneleri](http://msdn.microsoft.com/library/windows/desktop/dd144962) Windows SDK.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#77](../../mfc/codesnippet/cpp/cfont-class_8.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek HIERSVR](../../visual-cpp-samples.md)   
 [CGdiObject sınıfı](../../mfc/reference/cgdiobject-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



