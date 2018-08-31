---
title: CEditView sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bcc4af6f4aeb6c7a0df005d164729cf87065f613
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43220836"
---
# <a name="ceditview-class"></a>CEditView sınıfı
Düzenleme denetimi ve basit metin düzenleyici işlevselliği uygulamak için kullanılan bir Windows işlevlerini sağlar sınıfını görüntüle türü.  
  
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
|[CEditView::FindText](#findtext)|Metin içindeki bir dizeyi arar.|  
|[CEditView::GetBufferLength](#getbufferlength)|Karakter arabelleği uzunluğu alır.|  
|[CEditView::GetEditCtrl](#geteditctrl)|Erişim sağlayan `CEdit` kısmı bir `CEditView` nesne (Windows düzenleme denetimi).|  
|[CEditView::GetPrinterFont](#getprinterfont)|Geçerli yazıcı yazı tipini alır.|  
|[CEditView::GetSelectedText](#getselectedtext)|Geçerli metin seçimi alır.|  
|[CEditView::LockBuffer](#lockbuffer)|Arabellek kilitler.|  
|[CEditView::PrintInsideRect](#printinsiderect)|Belirli bir dikdörtgenin içindeki metni işler.|  
|[CEditView::SerializeRaw](#serializeraw)|Serileştiren bir `CEditView` ham metin olarak diske nesne.|  
|[CEditView::SetPrinterFont](#setprinterfont)|Yeni bir yazıcı yazı tipini ayarlar.|  
|[CEditView::SetTabStops](#settabstops)|Kümeleri durakları ekran görüntüsü hem de yazdırma için sekmesinde.|  
|[CEditView::UnlockBuffer](#unlockbuffer)|Arabellek kilidini açar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CEditView::OnFindNext](#onfindnext)|Bir metin dizesinin sonraki oluşumunu bulur.|  
|[CEditView::OnReplaceAll](#onreplaceall)|Belirli bir dize tüm oluşumlarını yeni bir dize ile değiştirir.|  
|[CEditView::OnReplaceSel](#onreplacesel)|Şu anki seçimi yerleştirir.|  
|[CEditView::OnTextNotFound](#ontextnotfound)|Herhangi bir metin eşleşmesi bulma işlemi başarısız olduğunda çağrılır.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CEditView::dwStyleDefault](#dwstyledefault)|Varsayılan Stil türü nesneler için `CEditView`.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CEditView` Sınıfı aşağıdaki ek işlevleri sağlar:  
  
-   Yazdırın.  
  
-   Bul ve Değiştir.  
  
 Çünkü sınıfı `CEditView` sınıfı türevi olan `CView`, sınıfın nesneleri `CEditView` belgeleri ve belge şablonları ile kullanılabilir.  
  
 Her `CEditView` denetimin metninin kendi genel bellek nesnesinde tutulur. Uygulamanızı herhangi bir sayıda olabilir `CEditView` nesneleri.  
  
 Türündeki nesneler oluşturma `CEditView` yukarıda listelenen eklenen işlevselliğe sahip bir düzenleme penceresi istiyorsanız veya basit metin düzenleyici işlevselliği istiyorsanız. A `CEditView` nesne pencere tüm istemci alanını kaplayacak. Kendi sınıflarından `CEditView` eklemek veya temel işlevlerini değiştirmek için ya da bir belge şablonuna eklenebilir sınıfları bildirme.  
  
 Sınıfın varsayılan uygulaması `CEditView` aşağıdaki komutları işleyen: ıd_edıt_select_all, ıd_edıt_fınd ıd_edıt_replace ıd_edıt_repeat ve ıd_fıle_prınt.  
  
 Varsayılan karakter sınırını `CEditView` olduğu (1024 \* 1048575 = 1024-1). Bu, temel alınan düzenleme denetiminin EM_LIMITTEXT işlevini çağırarak değiştirilebilir. Ancak, sınırları işletim sistemine göre farklılık gösterir ve türünü düzenleme denetimi (tek veya çok satırlı). Bu sınırlar hakkında daha fazla bilgi için bkz. [EM_LIMITTEXT](/windows/desktop/Controls/em-limittext).  
  
 Denetiminizin içinde bu sınırı değiştirmek için geçersiz kılın `OnCreate()` için işlev uygulamanızın `CEditView` sınıfı ve aşağıdaki kod satırını ekleyin:  
  
 [!code-cpp[NVC_MFCDocView#65](../../mfc/codesnippet/cpp/ceditview-class_1.cpp)]  
  
 Türündeki nesneler `CEditView` (veya türetilmiş türlerin `CEditView`) aşağıdaki sınırlamalara sahiptir:  
  
- `CEditView` TRUE uygulamıyor gördüğünüz (WYSIWYG) düzenleme aldığınızdır. Olduğunda bir seçim ekranında okunabilirlik ve eşleşen çıktılar, arasında `CEditView` ekran okunabilirlik açısından kabul eder.  
  
- `CEditView` yalnızca tek bir yazı tipinde metni görüntüleyebilirsiniz. Hiçbir özel karakter biçimlendirme desteklenir. Sınıfına bakın [CRichEditView](../../mfc/reference/cricheditview-class.md) büyük özelliklerin.  
  
-   Metin miktarını bir `CEditView` içerebilir sınırlıdır. Aynı limitlerdir `CEdit` denetimi.  
  
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
  
##  <a name="ceditview"></a>  CEditView::CEditView  
 Türünde bir nesne oluşturur `CEditView`.  
  
```  
CEditView();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne oluşturduktan sonra çağırmanız gerekir [CWnd::Create](../../mfc/reference/cwnd-class.md#create) düzenleme denetiminin kullanılmadan önce işlev. Öğesinden bir sınıf türetirseniz `CEditView` ve şablon kullanarak ekleyin `CWinApp::AddDocTemplate`, çerçevesi hem bu oluşturucuyu çağırır ve `Create` işlevi.  
  
##  <a name="dwstyledefault"></a>  CEditView::dwStyleDefault  
 Varsayılan stilini içeren `CEditView` nesne.  
  
```  
static const DWORD dwStyleDefault;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu statik bir üye olarak geçirmek *dwStyle* parametresinin `Create` işlevini varsayılan stilini alabilirsiniz `CEditView` nesne.  
  
##  <a name="findtext"></a>  CEditView::FindText  
 Çağrı `FindText` aranacak işlev `CEditView` nesnenin metin arabelleği.  
  
```  
BOOL FindText(
    LPCTSTR lpszFind,  
    BOOL bNext = TRUE,  
    BOOL bCase = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszFind*  
 Bulunacak metin.  
  
 *bİleri*  
 Arama yönünü belirtir. TRUE ise arama yönünü arabelleğin sonuna doğru ' dir. FALSE ise, arama yönünü arabellek doğru başlangıcıdır.  
  
 *bCase*  
 Arama büyük/küçük harfe duyarlı olup olmadığını belirtir. TRUE ise, arama büyük/küçük harfe duyarlıdır. FALSE ise, arama büyük/küçük harfe duyarlı değil.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Arama metni bulundu olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev metin tarafından belirtilen metin için arabellek arar *lpszFind*tarafından belirtilen yönde geçerli seçimi başlayan *bİleri*ile tarafındanbelirtilenbüyük/küçükharfeduyarlılık*bCase*. Metin bulunursa bulunan metinde seçimi ayarlar ve sıfır olmayan bir değer döndürür. Metin bulunamazsa, işlev 0 döndürür.  
  
 Normalde çağrı gerekmez `FindText` geçersiz kılmanız sürece işlev `OnFindNext`, çağıran `FindText`.  
  
##  <a name="getbufferlength"></a>  CEditView::GetBufferLength  
 Şu anda Sonlandırıcı null içermeden düzenleme denetiminin arabelleği karakter sayısını almak için bu üye işlevini çağırın.  
  
```  
UINT GetBufferLength() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dize arabelleği uzunluğu.  
  
##  <a name="geteditctrl"></a>  CEditView::GetEditCtrl  
 Çağrı `GetEditCtrl` düzenleme görünümü tarafından kullanılan düzenleme denetimine bir başvuru almak için.  
  
```  
CEdit& GetEditCtrl() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru bir `CEdit` nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu denetim türünde [CEdit](../../mfc/reference/cedit-class.md)kullanarak doğrudan Windows düzenleme denetimi değiştirebilirsiniz. Bu nedenle `CEdit` üye işlevleri.  
  
> [!CAUTION]
>  Kullanarak `CEdit` nesnesi değişiklik durumunu temel alınan Windows düzenleme denetimi. Örneğin, kullanarak sekme ayarlarını değiştirmemelisiniz [CEdit::SetTabStops](../../mfc/reference/cedit-class.md#settabstops) olduğundan işlev `CEditView` hem de düzenleme denetiminin yazdırmada kullanmak için bu ayarları önbelleğe alır. Bunun yerine, [CEditView::SetTabStops](#settabstops).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#66](../../mfc/codesnippet/cpp/ceditview-class_2.cpp)]  
  
##  <a name="getprinterfont"></a>  CEditView::GetPrinterFont  
 Çağrı `GetPrinterFont` işaretçisi almak için bir [CFont](../../mfc/reference/cfont-class.md) geçerli yazıcı yazı tipini açıklayan nesnesi.  
  
```  
CFont* GetPrinterFont() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CFont` geçerli yazıcı yazı tipi; belirten nesne Yazıcı yazı tipi ayarlanmamışsa yoksa NULL. İşaretçi geçici olabilir ve daha sonra kullanmak üzere saklanmalıdır değil.  
  
### <a name="remarks"></a>Açıklamalar  
 Yazıcı yazı tipi, varsayılan davranışını yazdırma ayarlanmamış ise `CEditView` görüntülemek için kullanılan yazı tipini kullanarak yazdırma sınıftır.  
  
 Geçerli yazıcı yazı tipi belirlemek için bu işlevi kullanın. İstenen yazıcı yazı tipi değil kullanırsanız [CEditView::SetPrinterFont](#setprinterfont) değiştirmek için.  
  
##  <a name="getselectedtext"></a>  CEditView::GetSelectedText  
 Çağrı `GetSelectedText` seçilen metne kopyalamak için bir `CString` seçim ya da seçimdeki ilk satır başı karakteri önceki karakter sonuna kadar bir nesne.  
  
```  
void GetSelectedText(CString& strResult) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *strResult*  
 Bir başvuru `CString` seçili metni almak için olan nesne.  
  
##  <a name="lockbuffer"></a>  CEditView::LockBuffer  
 Bir işaretçi arabelleğe almak için bu üye işlevini çağırın. Arabellek değiştirilmemelidir.  
  
```  
LPCTSTR LockBuffer() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düzenleme denetiminin arabellek için işaretçi.  
  
##  <a name="onfindnext"></a>  CEditView::OnFindNext  
 Metin olarak belirtilen metin için arabellek arar *lpszFind*, tarafından belirtilen yönde *bİleri*, büyük/küçük harfe duyarlılık tarafından belirtilen ile *bCase*.  
  
```  
virtual void OnFindNext(
    LPCTSTR lpszFind,  
    BOOL bNext,  
    BOOL bCase);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszFind*  
 Bulunacak metin.  
  
 *bİleri*  
 Arama yönünü belirtir. TRUE ise arama yönünü arabelleğin sonuna doğru ' dir. FALSE ise, arama yönünü arabellek doğru başlangıcıdır.  
  
 *bCase*  
 Arama büyük/küçük harfe duyarlı olup olmadığını belirtir. TRUE ise, arama büyük/küçük harfe duyarlıdır. FALSE ise, arama büyük/küçük harfe duyarlı değil.  
  
### <a name="remarks"></a>Açıklamalar  
 Arama geçerli seçimi başlangıcında başlar ve yapılan bir çağrıyla gerçekleştirilir [FindText](#findtext). Varsayılan uygulamada, `OnFindNext` çağrıları [OnTextNotFound](#ontextnotfound) metin bulunmazsa.  
  
 Geçersiz kılma `OnFindNext` şeklini değiştirmek için bir `CEditView`-türetilmiş nesneden metin araması yapar. `CEditView` çağrıları `OnFindNext` , kullanıcının seçtiği Sonrakini Bul düğmesini standart Bul iletişim kutusunda.  
  
##  <a name="onreplaceall"></a>  CEditView::OnReplaceAll  
 `CEditView` çağrıları `OnReplaceAll` kullanıcı standart Değiştir iletişim kutusunda Tümünü Değiştir düğmesini seçtiğinde.  
  
```  
virtual void OnReplaceAll(
    LPCTSTR lpszFind,  
    LPCTSTR lpszReplace,  
    BOOL bCase);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszFind*  
 Bulunacak metin.  
  
 *lpszReplace*  
 Arama metni değiştirilecek metni.  
  
 *bCase*  
 Arama büyük/küçük harfe duyarlı olup olmadığını belirtir. TRUE ise, arama büyük/küçük harfe duyarlıdır. FALSE ise, arama büyük/küçük harfe duyarlı değil.  
  
### <a name="remarks"></a>Açıklamalar  
 `OnReplaceAll` metin olarak belirtilen metin için arabellek arar *lpszFind*, büyük/küçük harfe duyarlılık tarafından belirtilen ile *bCase*. Arama geçerli seçimin başlangıçtan başlar. Her arama metni bulunamadı, bu işlev, oluşumunu metin tarafından belirtilen metinle değiştirir. *lpszReplace*. Arama yapılan bir çağrıyla gerçekleştirilir [FindText](#findtext). Varsayılan uygulamada, [OnTextNotFound](#ontextnotfound) metin bulunamazsa çağrılır.  
  
 Geçerli seçimi eşleşmiyorsa *lpszFind*, seçimi tarafından belirtilen metnin ilk geçtiği yere güncelleştirilir *lpszFind* ve bir değiştirme gerçekleştirilemiyor. Bu, kullanıcının bu seçimi değiştirilecek metni eşleşmediğinde yapmak istediğini olduğunu onaylamak sağlar.  
  
 Geçersiz kılma `OnReplaceAll` şeklini değiştirmek için bir `CEditView`-türetilmiş nesneden metin değiştirir.  
  
##  <a name="onreplacesel"></a>  CEditView::OnReplaceSel  
 `CEditView` çağrıları `OnReplaceSel` kullanıcı standart Değiştir iletişim kutusunda Değiştir düğmesini seçtiğinde.  
  
```  
virtual void OnReplaceSel(
    LPCTSTR lpszFind,  
    BOOL bNext,  
    BOOL bCase,  
    LPCTSTR lpszReplace);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszFind*  
 Bulunacak metin.  
  
 *bİleri*  
 Arama yönünü belirtir. TRUE ise arama yönünü arabelleğin sonuna doğru ' dir. FALSE ise, arama yönünü arabellek doğru başlangıcıdır.  
  
 *bCase*  
 Arama büyük/küçük harfe duyarlı olup olmadığını belirtir. TRUE ise, arama büyük/küçük harfe duyarlıdır. FALSE ise, arama büyük/küçük harfe duyarlı değil.  
  
 *lpszReplace*  
 Bulunan metni değiştirilecek metni.  
  
### <a name="remarks"></a>Açıklamalar  
 Seçimi değiştirildikten sonra bu işlevi metin Sonrakini tarafından belirtilen metin için arabellek arar *lpszFind*, tarafından belirtilen yönde *bİleri*, büyük/küçük harfe duyarlılık ile tarafından belirtilen *bCase*. Arama yapılan bir çağrıyla gerçekleştirilir [FindText](#findtext). Metin bulunamazsa [OnTextNotFound](#ontextnotfound) çağrılır.  
  
 Geçersiz kılma `OnReplaceSel` şeklini değiştirmek için bir `CEditView`-türetilmiş nesnenin seçili metni değiştirir.  
  
##  <a name="ontextnotfound"></a>  CEditView::OnTextNotFound  
 Windows işlevini çağıran varsayılan uygulamayı değiştirmek için bu işlevi geçersiz kılma `MessageBeep`.  
  
```  
virtual void OnTextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszFind*  
 Bulunacak metin.  
  
##  <a name="printinsiderect"></a>  CEditView::PrintInsideRect  
 Çağrı `PrintInsideRect` tarafından belirtilen dikdörtgenin içindeki metni yazdırmak için *rectLayout*.  
  
```  
UINT PrintInsideRect(
    CDC *pDC,  
    RECT& rectLayout,  
    UINT nIndexStart,  
    UINT nIndexStop);
```  
  
### <a name="parameters"></a>Parametreler  
 *pDC*  
 Yazıcı cihaz bağlamı işaretçisi.  
  
 *rectLayout*  
 Başvuru bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesne veya [RECT yapısı](../../mfc/reference/rect-structure1.md) metin olduğu işlenecek dikdörtgen belirtme.  
  
 *nIndexStart*  
 İşlenecek ilk karakterin arabellek içinde dizin.  
  
 *nIndexStop*  
 İşlenecek son karakter izleyen karakterin arabellek içinde dizin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yazdırılacak sıradaki karakterin dizini (diğer bir deyişle, işlenen son karakter karakter).  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `CEditView` denetim stili ES_AUTOHSCROLL yok, metin işleme dikdörtgen içinde kaydırılır. Denetim stili ES_AUTOHSCROLL varsa, bu metin dikdörtgenin sağ kenarda kırpılır.  
  
 `rect.bottom` Öğesinin *rectLayout* metne göre dolu özgün dikdörtgen parçası dikdörtgenin boyutlarını tanımlamak için nesne değiştirilir.  
  
##  <a name="serializeraw"></a>  CEditView::SerializeRaw  
 Çağrı `SerializeRaw` sağlamak için bir `CArchive` nesne okuma veya metin yazmak `CEditView` bir metin dosyasına nesne.  
  
```  
void SerializeRaw(CArchive& ar);
```  
  
### <a name="parameters"></a>Parametreler  
 *ar*  
 Başvuru `CArchive` seri hale getirilmiş metin depolayan bir nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 `SerializeRaw` farklıdır `CEditView`'s, iç uygulama `Serialize` okur ve yalnızca metin, nesne açıklama verilerini önceki olmadan yazar.  
  
##  <a name="setprinterfont"></a>  CEditView::SetPrinterFont  
 Çağrı `SetPrinterFont` tarafından belirtilen yazı tipi yazıcı yazı tipi koymak için *pFont*.  
  
```  
void SetPrinterFont(CFont* pFont);
```  
  
### <a name="parameters"></a>Parametreler  
 *pFont*  
 Türü bir nesneye bir işaretçi `CFont`. NULL ise, yazdırma için kullanılan yazıtipi görünen yazı tipini alır.  
  
### <a name="remarks"></a>Açıklamalar  
 Görünümünüzü her zaman belirli bir yazı tipi yazdırma için kullanmak istiyorsanız, bir çağrı ekleyin `SetPrinterFont` sınıfınızın içinde `OnPreparePrinting` işlevi. Yazdırma gerçekleşmeden önce görünümün içeriğini yazdırılır önce yazı tipi değişiklik gerçekleşmeden şekilde bu sanal işlev çağrılır.  
  
##  <a name="settabstops"></a>  CEditView::SetTabStops  
 Görüntüleme ve yazdırma için kullanılan sekme durakları ayarlamak için bu işlevi çağırın.  
  
```  
void SetTabStops(int nTabStops);
```  
  
### <a name="parameters"></a>Parametreler  
 *nTabStops*  
 İletişim kutusu birimlerinde her sekme durağı genişliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca tek bir sekme durağı genişliği desteklenir. ( `CEdit` nesneleri birden çok sekme genişliği destekler.) Eşit dörtte biri (büyük ve küçük harf alfabetik karakterleri üzerinde yalnızca bağlı olarak) ortalama karakter genişliği yazdırma veya görüntüleme sırasında kullanılan yazı tipi iletişim kutusu birimlerinde, genişliklerini var. Kullanmamalısınız `CEdit::SetTabStops` çünkü `CEditView` sekme durağı değerini önbelleğe gerekir.  
  
 Bu işlev yalnızca sekmeler için çağırıldığı nesnenin değiştirir. Sekme değiştirmek için her biri için durdurur `CEditView` uygulamanızda nesnesi, her nesnenin `SetTabStops` işlevi.  
  
### <a name="example"></a>Örnek  
 Bu kod parçasını sekme durakları her dördüncü karakterin denetime ekleyeceğini yazı tipi ölçerek dikkatli bir şekilde ayarlar.  
  
 [!code-cpp[NVC_MFCDocView#67](../../mfc/codesnippet/cpp/ceditview-class_3.cpp)]  
  
##  <a name="unlockbuffer"></a>  CEditView::UnlockBuffer  
 Arabellek kilidini açmak için bu üye işlevini çağırın.  
  
```  
void UnlockBuffer() const;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı `UnlockBuffer` tarafından döndürülen işaretçi'ı kullanmayı bitirdikten sonra [LockBuffer](#lockbuffer).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek SUPERPAD](../../visual-cpp-samples.md)   
 [CCtrlView sınıfı](../../mfc/reference/cctrlview-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CEdit sınıfı](../../mfc/reference/cedit-class.md)   
 [CDocument sınıfı](../../mfc/reference/cdocument-class.md)   
 [CDocTemplate sınıfı](../../mfc/reference/cdoctemplate-class.md)   
 [CCtrlView sınıfı](../../mfc/reference/cctrlview-class.md)   
 [CRichEditView Sınıfı](../../mfc/reference/cricheditview-class.md)
