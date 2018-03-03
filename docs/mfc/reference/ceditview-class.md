---
title: "CEditView sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CEditView
- AFXEXT/CEditView
- AFXEXT/CEditView::CEditView
- AFXEXT/CEditView::FindText
- AFXEXT/CEditView::GetBufferLength
- AFXEXT/CEditView::GetEditCtrl
- AFXEXT/CEditView::GetPrinterFont
- AFXEXT/CEditView::GetSelectedText
- AFXEXT/CEditView::LockBuffer
- AFXEXT/CEditView::PrintInsideRect
- AFXEXT/CEditView::SerializeRaw
- AFXEXT/CEditView::SetPrinterFont
- AFXEXT/CEditView::SetTabStops
- AFXEXT/CEditView::UnlockBuffer
- AFXEXT/CEditView::OnFindNext
- AFXEXT/CEditView::OnReplaceAll
- AFXEXT/CEditView::OnReplaceSel
- AFXEXT/CEditView::OnTextNotFound
- AFXEXT/CEditView::dwStyleDefault
dev_langs:
- C++
helpviewer_keywords:
- CEditView [MFC], CEditView
- CEditView [MFC], FindText
- CEditView [MFC], GetBufferLength
- CEditView [MFC], GetEditCtrl
- CEditView [MFC], GetPrinterFont
- CEditView [MFC], GetSelectedText
- CEditView [MFC], LockBuffer
- CEditView [MFC], PrintInsideRect
- CEditView [MFC], SerializeRaw
- CEditView [MFC], SetPrinterFont
- CEditView [MFC], SetTabStops
- CEditView [MFC], UnlockBuffer
- CEditView [MFC], OnFindNext
- CEditView [MFC], OnReplaceAll
- CEditView [MFC], OnReplaceSel
- CEditView [MFC], OnTextNotFound
- CEditView [MFC], dwStyleDefault
ms.assetid: bf38255c-fcbe-450c-95b2-3c5e35f86c37
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 78aa34f1790b2e86dae183b96c88b4ed35483927
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ceditview-class"></a>CEditView sınıfı
Bir Windows işlevselliğini sağlar görünüm sınıfının bir türü denetim düzenleyin ve basit bir metin düzenleyicisi işlevselliği uygulamak için kullanılabilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CEditView : public CCtrlView  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CEditView::CEditView](#ceditview)|Türünde bir nesne oluşturur `CEditView`.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CEditView::FindText](#findtext)|Metnin içindeki bir dize arar.|  
|[CEditView::GetBufferLength](#getbufferlength)|Karakter arabelleği uzunluğunu alır.|  
|[CEditView::GetEditCtrl](#geteditctrl)|Erişim sağlayan `CEdit` kısmı bir `CEditView` nesnesi (Windows Denetim Düzenle).|  
|[CEditView::GetPrinterFont](#getprinterfont)|Geçerli yazıcı yazı tipini alır.|  
|[CEditView::GetSelectedText](#getselectedtext)|Geçerli metin seçimi alır.|  
|[CEditView::LockBuffer](#lockbuffer)|Arabellek kilitler.|  
|[CEditView::PrintInsideRect](#printinsiderect)|İçindeki verilen dikdörtgene metin işler.|  
|[CEditView::SerializeRaw](#serializeraw)|Serileştiren bir `CEditView` ham metin olarak diske nesnesi.|  
|[CEditView::SetPrinterFont](#setprinterfont)|Yeni bir yazıcı yazı tipi ayarlar.|  
|[CEditView::SetTabStops](#settabstops)|Sekme durakları ekran görüntüsü hem de yazdırma için ayarlar.|  
|[CEditView::UnlockBuffer](#unlockbuffer)|Arabellek kilidini açar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CEditView::OnFindNext](#onfindnext)|Bir metin dizesinin sonrakini bulur.|  
|[CEditView::OnReplaceAll](#onreplaceall)|Belirtilen dizenin tüm oluşumlarını yeni bir dizeyle değiştirir.|  
|[CEditView::OnReplaceSel](#onreplacesel)|Geçerli seçim yerini alır.|  
|[CEditView::OnTextNotFound](#ontextnotfound)|Herhangi bir başka metin eşleştirmek bir bulma işlemi başarısız olduğunda çağrılır.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CEditView::dwStyleDefault](#dwstyledefault)|Stil türündeki nesneler için varsayılan **CEditView.**|  
  
## <a name="remarks"></a>Açıklamalar  
 `CEditView` Sınıfı, aşağıdaki ek işlevleri sağlar:  
  
-   Yazdırma.  
  
-   Bul ve Değiştir.  
  
 Çünkü sınıfı `CEditView` sınıfı bir türevi değil `CView`, sınıfın nesnelerini `CEditView` belgeleri ve belge şablonları ile kullanılabilir.  
  
 Her `CEditView` denetimin metin kendi genel bellek nesnesinde tutulur. Uygulamanız herhangi bir sayıda olabilir `CEditView` nesneleri.  
  
 Türündeki nesneleri oluşturma `CEditView` yukarıda listelenen eklenen işlevselliğe sahip bir düzenleme penceresi istiyorsanız veya basit metin düzenleyici işlevselliği istiyorsanız. A `CEditView` nesne bir pencere tüm istemci alanını kaplar. Kendi sınıflarından `CEditView` eklemek veya temel işlevlerini değiştirmek için ya da bir belge şablonu eklenen sınıflar bildirmeniz.  
  
 Varsayılan uygulama sınıfının `CEditView` aşağıdaki komutları işler: **ıd_edıt_select_all**, **ıd_edıt_fınd**, **ıd_edıt_replace**, **Id_edıt_repeat**, ve **ıd_fıle_prınt**.  
  
 Varsayılan karakter sınırını `CEditView` olduğu (1024 \* 1048575 = 1024-1). Bu çağırarak değiştirilebilir **EM_LIMITTEXT** temel işlevi düzenleme denetimi. Ancak, sınırlar işletim sistemine bağlı olarak farklı ve türünü düzenleme denetimi (tek veya çok satırlı). Bu sınırları hakkında daha fazla bilgi için bkz: [EM_LIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761607).  
  
 Denetim bu sınırı değiştirmek için geçersiz kılma `OnCreate()` için işlev, `CEditView` sınıfı ve aşağıdaki kod satırını ekleyin:  
  
 [!code-cpp[NVC_MFCDocView#65](../../mfc/codesnippet/cpp/ceditview-class_1.cpp)]  
  
 Nesne türü `CEditView` (veya türetilen türlerin `CEditView`) aşağıdaki sınırlamalara sahiptir:  
  
- `CEditView`TRUE uygulamıyor gördüğünüz (WYSIWYG) düzenleme aldığınızdır. Söz konusu olduğunda bir seçim ekranında okunabilirlik ile eşleşen çıktılar, arasında `CEditView` ekran okunabilirlik için kabul eder.  
  
- `CEditView`metin yalnızca tek bir yazı tipinde görüntüleyebilirsiniz. Hiçbir özel karakter biçimlendirme desteklenir. Sınıfına bakın [CRichEditView](../../mfc/reference/cricheditview-class.md) büyük özellikleri.  
  
-   Metin miktarını bir `CEditView` içerebilir sınırlıdır. Sınırları aynıdır `CEdit` denetim.  
  
 Daha fazla bilgi için `CEditView`, bkz: [türetilmiş görünüm sınıfları kullanılabilir MFC'de](../../mfc/derived-view-classes-available-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CEditView`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxext.h  
  
##  <a name="ceditview"></a>CEditView::CEditView  
 Türünde bir nesne oluşturur `CEditView`.  
  
```  
CEditView();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne oluşturma sonra çağırmalısınız [CWnd::Create](../../mfc/reference/cwnd-class.md#create) düzenleme denetimi kullanılmadan önce işlev. Öğesinden bir sınıf türetirseniz `CEditView` ve şablonu kullanarak eklemek `CWinApp::AddDocTemplate`, çerçevesi hem bu oluşturucuyu çağırır ve **oluşturma** işlevi.  
  
##  <a name="dwstyledefault"></a>CEditView::dwStyleDefault  
 Varsayılan stilini içeren `CEditView` nesnesi.  
  
```  
static const DWORD dwStyleDefault;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu statik üye olarak geçirmek `dwStyle` parametresinin **oluşturma** işlevi için varsayılan stil elde `CEditView` nesnesi.  
  
##  <a name="findtext"></a>CEditView::FindText  
 Çağrı `FindText` aramak için işlevi `CEditView` nesnenin metin arabelleği.  
  
```  
BOOL FindText(
    LPCTSTR lpszFind,  
    BOOL bNext = TRUE,  
    BOOL bCase = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszFind`  
 Bulunacak metin.  
  
 `bNext`  
 Arama yönünü belirtir. Varsa **doğru**, Arama yönü arabelleğin sonuna doğru olur. Varsa **yanlış**, arama yönünü arabellek doğru başlangıcıdır.  
  
 `bCase`  
 Arama büyük küçük harfe duyarlı olup olmadığını belirtir. Varsa **doğru**, arama büyük küçük harfe duyarlıdır. Varsa **yanlış**, arama büyük küçük harfe duyarlı değildir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aranacak metin bulunursa, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev tarafından belirtilen metin arabelleği metni arar `lpszFind`tarafından belirtilen yönde geçerli seçim başlayarak `bNext`ve büyük/küçük harfe duyarlılık tarafından belirtilen ile `bCase`. Metin bulunursa, bulunan metinde seçimi ayarlar ve sıfır olmayan bir değer döndürür. Metin bulunamazsa işlevi 0 değerini döndürür.  
  
 Normalde çağrı gerekmez `FindText` kılmanız sürece işlev `OnFindNext`, çağıran `FindText`.  
  
##  <a name="getbufferlength"></a>CEditView::GetBufferLength  
 Şu anda null Sonlandırıcı hariç düzenleme denetimin arabellek karakter sayısını elde etmek için bu üye işlevini çağırın.  
  
```  
UINT GetBufferLength() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Arabellekteki dize uzunluğu.  
  
##  <a name="geteditctrl"></a>CEditView::GetEditCtrl  
 Çağrı `GetEditCtrl` düzenleme görünümü tarafından kullanılan düzenleme denetimi başvuru alınamıyor.  
  
```  
CEdit& GetEditCtrl() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru bir `CEdit` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu denetim türünde [CEdit](../../mfc/reference/cedit-class.md), kullanarak doğrudan Windows düzenleme denetimi işleyebileceğiniz şekilde `CEdit` üye işlevleri.  
  
> [!CAUTION]
>  Kullanarak `CEdit` değişiklik temel alınan Windows durumunu düzenleyebilirsiniz denetim nesnesi. Örneğin, sekme ayarlarını kullanarak değiştirmemelisiniz [CEdit::SetTabStops](../../mfc/reference/cedit-class.md#settabstops) çünkü işlev `CEditView` düzenleme denetimindeki hem yazdırma kullanmak için bu ayarları önbelleğe alır. Bunun yerine, kullanın [CEditView::SetTabStops](#settabstops).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#66](../../mfc/codesnippet/cpp/ceditview-class_2.cpp)]  
  
##  <a name="getprinterfont"></a>CEditView::GetPrinterFont  
 Çağrı `GetPrinterFont` gösteren bir işaretçi almak için bir [CFont](../../mfc/reference/cfont-class.md) geçerli yazıcı yazı tipi tanımlar nesnesi.  
  
```  
CFont* GetPrinterFont() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CFont` geçerli yazıcı yazı tipi; belirtir nesnesi **NULL** yazıcı yazı tipi ayarlanmamış ise. İşaretçinin geçici olabilir ve daha sonra kullanmak üzere depolanmadığından.  
  
### <a name="remarks"></a>Açıklamalar  
 Yazıcı yazı tipi, davranışını yazdırma varsayılan ayarlanmamış ise `CEditView` sınıftır görüntülemek için kullanılan aynı yazı tipi kullanarak yazdırma.  
  
 Geçerli yazıcı yazı tipi belirlemek için bu işlevi kullanın. İstenen yazıcı yazı tipi değilse, [CEditView::SetPrinterFont](#setprinterfont) değiştirmek için.  
  
##  <a name="getselectedtext"></a>CEditView::GetSelectedText  
 Çağrı `GetSelectedText` seçili metne kopyalamak için bir `CString` seçimi veya seçim ilk satır başı karakteri önceki karakter sonuna kadar nesnesi.  
  
```  
void GetSelectedText(CString& strResult) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `strResult`  
 Bir başvuru `CString` seçili metni almak için nesne.  
  
##  <a name="lockbuffer"></a>CEditView::LockBuffer  
 Arabellek için bir işaretçi almak için bu üye işlevini çağırın. Arabellek değiştirilmemelidir.  
  
```  
LPCTSTR LockBuffer() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düzenle denetim arabellek için bir işaretçi.  
  
##  <a name="onfindnext"></a>CEditView::OnFindNext  
 Tarafından belirlenen metin arabelleği metni arar `lpszFind`, belirtilen yönde `bNext`, büyük/küçük harfe duyarlılık tarafından belirtilen ile `bCase`.  
  
```  
virtual void OnFindNext(
    LPCTSTR lpszFind,  
    BOOL bNext,  
    BOOL bCase);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszFind`  
 Bulunacak metin.  
  
 `bNext`  
 Arama yönünü belirtir. Varsa **doğru**, Arama yönü arabelleğin sonuna doğru olur. Varsa **yanlış**, arama yönünü arabellek doğru başlangıcıdır.  
  
 `bCase`  
 Arama büyük küçük harfe duyarlı olup olmadığını belirtir. Varsa **doğru**, arama büyük küçük harfe duyarlıdır. Varsa **yanlış**, arama büyük küçük harfe duyarlı değildir.  
  
### <a name="remarks"></a>Açıklamalar  
 Arama geçerli seçim başında başlar ve bir çağrı aracılığıyla gerçekleştirilir [FindText](#findtext). Varsayılan uygulamada `OnFindNext` çağrıları [OnTextNotFound](#ontextnotfound) metin bulunmazsa.  
  
 Geçersiz kılma `OnFindNext` şeklini değiştirmek için bir `CEditView`-türetilen nesne metin arar. `CEditView`çağrıları `OnFindNext` zaman kullanıcının seçtiği Sonrakini Bul düğmesi standart Bul iletişim kutusunda.  
  
##  <a name="onreplaceall"></a>CEditView::OnReplaceAll  
 `CEditView`çağrıları `OnReplaceAll` kullanıcı standart Değiştir iletişim kutusunda Tümünü Değiştir düğmesini seçtiğinde.  
  
```  
virtual void OnReplaceAll(
    LPCTSTR lpszFind,  
    LPCTSTR lpszReplace,  
    BOOL bCase);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszFind`  
 Bulunacak metin.  
  
 `lpszReplace`  
 Arama metni değiştirmek için metin.  
  
 `bCase`  
 Arama büyük küçük harfe duyarlı olup olmadığını belirtir. Varsa **doğru**, arama büyük küçük harfe duyarlıdır. Varsa **yanlış**, arama büyük küçük harfe duyarlı değildir.  
  
### <a name="remarks"></a>Açıklamalar  
 `OnReplaceAll`tarafından belirlenen metin arabelleği metni arar `lpszFind`, büyük/küçük harfe duyarlılık tarafından belirtilen ile `bCase`. Arama geçerli seçim başında başlar. Aranacak metin bulunursa, her zaman bu işlev tarafından belirtilen metin ile metnin meydana değiştirir `lpszReplace`. Arama çağrısı aracılığıyla gerçekleştirilir [FindText](#findtext). Varsayılan uygulamada [OnTextNotFound](#ontextnotfound) metin bulunmazsa olarak adlandırılır.  
  
 Geçerli seçim eşleşmiyorsa `lpszFind`, seçim tarafından belirtilen metnin ilk geçtiği için güncelleştirilmiş `lpszFind` ve değiştirme gerçekleştirilemiyor. Bu seçimin değiştirilmeleri metin eşleşmediğinde yapmak istedikleri olduğunu onaylamak kullanıcı sağlar.  
  
 Geçersiz kılma `OnReplaceAll` şeklini değiştirmek için bir `CEditView`-türetilen nesne metin yerini alır.  
  
##  <a name="onreplacesel"></a>CEditView::OnReplaceSel  
 `CEditView`çağrıları `OnReplaceSel` kullanıcı standart Değiştir iletişim kutusunda Değiştir düğmesini seçtiğinde.  
  
```  
virtual void OnReplaceSel(
    LPCTSTR lpszFind,  
    BOOL bNext,  
    BOOL bCase,  
    LPCTSTR lpszReplace);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszFind`  
 Bulunacak metin.  
  
 `bNext`  
 Arama yönünü belirtir. Varsa **doğru**, Arama yönü arabelleğin sonuna doğru olur. Varsa **yanlış**, arama yönünü arabellek doğru başlangıcıdır.  
  
 `bCase`  
 Arama büyük küçük harfe duyarlı olup olmadığını belirtir. Varsa **doğru**, arama büyük küçük harfe duyarlıdır. Varsa **yanlış**, arama büyük küçük harfe duyarlı değildir.  
  
 `lpszReplace`  
 Bulunan metni değiştirmek için metin.  
  
### <a name="remarks"></a>Açıklamalar  
 Seçim değiştirildikten sonra bu işlev metni Sonrakini tarafından belirtilen metin arabelleği arar `lpszFind`, belirtilen yönde `bNext`, büyük/küçük harfe duyarlılık tarafından belirtilen ile `bCase`. Arama çağrısı aracılığıyla gerçekleştirilir [FindText](#findtext). Metin bulunamazsa [OnTextNotFound](#ontextnotfound) olarak adlandırılır.  
  
 Geçersiz kılma `OnReplaceSel` şeklini değiştirmek için bir `CEditView`-türetilen nesne seçili metnin yerini alır.  
  
##  <a name="ontextnotfound"></a>CEditView::OnTextNotFound  
 Windows işlev çağrılarını varsayılan uygulaması değiştirmek için bu işlevi geçersiz **MessageBeep**.  
  
```  
virtual void OnTextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszFind`  
 Bulunacak metin.  
  
##  <a name="printinsiderect"></a>CEditView::PrintInsideRect  
 Çağrı `PrintInsideRect` tarafından belirtilen dikdörtgeni metinde yazdırmak için *rectLayout*.  
  
```  
UINT PrintInsideRect(
    CDC *pDC,  
    RECT& rectLayout,  
    UINT nIndexStart,  
    UINT nIndexStop);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Yazıcı cihaz bağlamı işaretçi.  
  
 *rectLayout*  
 Başvuru bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesne veya [RECT yapısı](../../mfc/reference/rect-structure1.md) metin olduğu işlenmek üzere dikdörtgen belirtme.  
  
 `nIndexStart`  
 İşlenmek üzere ilk karakter arabellek içinde dizin.  
  
 `nIndexStop`  
 İşlenmek üzere son harfinden karakter arabellek içinde dizin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yazdırılacak sonraki karakter dizinini (diğer bir deyişle, işlenen son harfinden karakter).  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `CEditView` denetim stili yok **ES_AUTOHSCROLL**, metin işleme dikdörtgenin sarılır. Denetim stili varsa **ES_AUTOHSCROLL**, metnin sağ köşesine dikdörtgen kırpılır.  
  
 **Rect.bottom** öğesinin *rectLayout* nesnesi, böylece metin tarafından dolu özgün dikdörtgen parçası dikdörtgenin boyutlarını tanımlamak değiştirilir.  
  
##  <a name="serializeraw"></a>CEditView::SerializeRaw  
 Çağrı `SerializeRaw` sağlamak için bir `CArchive` nesne okuma veya metin yazmak `CEditView` bir metin dosyasına nesne.  
  
```  
void SerializeRaw(CArchive& ar);
```  
  
### <a name="parameters"></a>Parametreler  
 `ar`  
 Başvuru `CArchive` serileştirilmiş metni depolar nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 `SerializeRaw`farklı `CEditView`'s iç uyarlamasını `Serialize` okur ve metin yalnızca nesne açıklama verilerini önceki olmadan yazar.  
  
##  <a name="setprinterfont"></a>CEditView::SetPrinterFont  
 Çağrı `SetPrinterFont` tarafından belirtilen yazı tipi için yazıcı yazı tipi ayarlamak için `pFont`.  
  
```  
void SetPrinterFont(CFont* pFont);
```  
  
### <a name="parameters"></a>Parametreler  
 `pFont`  
 Bir nesne türü için bir işaretçi `CFont`. Varsa **NULL**, yazdırma için kullanılan yazı tipi görüntü yazı tipini dayanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Her zaman belirli bir yazı tipi yazdırmak için kullanmak üzere, görünüm istiyorsanız, bir çağrı ekleyin `SetPrinterFont` sınıfınızın içinde `OnPreparePrinting` işlevi. Yazdırma oluşmadan önce görünümün içeriği yazdırılır önce yazı tipi değişiklik gerçekleşmeden şekilde bu sanal işlev çağrılır.  
  
##  <a name="settabstops"></a>CEditView::SetTabStops  
 Görüntüleme ve yazdırma için kullanılan sekme durakları ayarlamak için bu işlevini çağırın.  
  
```  
void SetTabStops(int nTabStops);
```  
  
### <a name="parameters"></a>Parametreler  
 `nTabStops`  
 İletişim kutusu birimleri içinde her sekme durağı genişliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca tek bir sekme durağı genişliği desteklenir. ( `CEdit` nesneleri birden çok sekme genişliği destekler.) Genişlikleri yazdırma veya görüntüleme sırasında kullanılan yazı tipi ortalama karakter genişliğini (büyük ve küçük harf alfasayısal karakterler üzerinde yalnızca göre), bir dördüncü eşit iletişim kutusu birimleri bulunmaktadır. Kullanılamaz `CEdit::SetTabStops` çünkü `CEditView` sekme durağı değerini önbelleğe gerekir.  
  
 Bu işlev yalnızca sekmeler için çağırıldığı nesnenin değiştirir. Sekme değiştirmek için her biri için durdurur `CEditView` nesne uygulamanızda, her nesnenin çağrı `SetTabStops` işlevi.  
  
### <a name="example"></a>Örnek  
 Bu kod parçası sekme durakları her dördüncü karakter denetimine dikkatle ekleyeceğini yazı tipi ölçerek ayarlar.  
  
 [!code-cpp[NVC_MFCDocView#67](../../mfc/codesnippet/cpp/ceditview-class_3.cpp)]  
  
##  <a name="unlockbuffer"></a>CEditView::UnlockBuffer  
 Arabellek kilidini açmak için bu üye işlevini çağırın.  
  
```  
void UnlockBuffer() const;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı `UnlockBuffer` tarafından döndürülen işaretçi kullanmayı bitirdikten sonra [LockBuffer](#lockbuffer).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek SUPERPAD](../../visual-cpp-samples.md)   
 [CCtrlView sınıfı](../../mfc/reference/cctrlview-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CEdit sınıfı](../../mfc/reference/cedit-class.md)   
 [CDocument sınıfı](../../mfc/reference/cdocument-class.md)   
 [CDocTemplate sınıfı](../../mfc/reference/cdoctemplate-class.md)   
 [CCtrlView sınıfı](../../mfc/reference/cctrlview-class.md)   
 [CRichEditView Sınıfı](../../mfc/reference/cricheditview-class.md)
