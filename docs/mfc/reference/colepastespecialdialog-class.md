---
title: COlePasteSpecialDialog sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog::COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog::AddFormat
- AFXODLGS/COlePasteSpecialDialog::AddLinkEntry
- AFXODLGS/COlePasteSpecialDialog::AddStandardFormats
- AFXODLGS/COlePasteSpecialDialog::CreateItem
- AFXODLGS/COlePasteSpecialDialog::DoModal
- AFXODLGS/COlePasteSpecialDialog::GetDrawAspect
- AFXODLGS/COlePasteSpecialDialog::GetIconicMetafile
- AFXODLGS/COlePasteSpecialDialog::GetPasteIndex
- AFXODLGS/COlePasteSpecialDialog::GetSelectionType
- AFXODLGS/COlePasteSpecialDialog::m_ps
dev_langs:
- C++
helpviewer_keywords:
- COlePasteSpecialDialog [MFC], COlePasteSpecialDialog
- COlePasteSpecialDialog [MFC], AddFormat
- COlePasteSpecialDialog [MFC], AddLinkEntry
- COlePasteSpecialDialog [MFC], AddStandardFormats
- COlePasteSpecialDialog [MFC], CreateItem
- COlePasteSpecialDialog [MFC], DoModal
- COlePasteSpecialDialog [MFC], GetDrawAspect
- COlePasteSpecialDialog [MFC], GetIconicMetafile
- COlePasteSpecialDialog [MFC], GetPasteIndex
- COlePasteSpecialDialog [MFC], GetSelectionType
- COlePasteSpecialDialog [MFC], m_ps
ms.assetid: 0e82ef9a-9bbe-457e-8240-42c86a0534f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5e2e668a2ad15ec9ec2fb779be32d35c17eb57cc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374363"
---
# <a name="colepastespecialdialog-class"></a>COlePasteSpecialDialog sınıfı
OLE Özel Yapıştır iletişim kutusu için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COlePasteSpecialDialog : public COleDialog  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COlePasteSpecialDialog::COlePasteSpecialDialog](#colepastespecialdialog)|Oluşturan bir `COlePasteSpecialDialog` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COlePasteSpecialDialog::AddFormat](#addformat)|Özel biçimler uygulamanızı yapıştırabilirsiniz biçimleri listesine ekler.|  
|[COlePasteSpecialDialog::AddLinkEntry](#addlinkentry)|Yeni bir giriş desteklenen Pano biçimleri listesine ekler.|  
|[COlePasteSpecialDialog::AddStandardFormats](#addstandardformats)|Ekler **CF_BITMAP**, **CF_DIB**, `CF_METAFILEPICT`ve isteğe bağlı olarak `CF_LINKSOURCE` biçimlerinin listesi için uygulamanızın yapıştırabilirsiniz.|  
|[COlePasteSpecialDialog::CreateItem](#createitem)|Öğe kapsayıcı belgenin belirtilen biçimi kullanarak oluşturur.|  
|[COlePasteSpecialDialog::DoModal](#domodal)|OLE Özel Yapıştır iletişim kutusunu görüntüler.|  
|[COlePasteSpecialDialog::GetDrawAspect](#getdrawaspect)|Veya öğeyi simge olarak çizileceğini belirtir.|  
|[COlePasteSpecialDialog::GetIconicMetafile](#geticonicmetafile)|Bu öğe simge formla ilişkili meta dosyası için bir tanıtıcı alır.|  
|[COlePasteSpecialDialog::GetPasteIndex](#getpasteindex)|Kullanıcı tarafından seçilen kullanılabilir yapıştırma seçenekleri dizinini alır.|  
|[COlePasteSpecialDialog::GetSelectionType](#getselectiontype)|Seçilen seçim türünü alır.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COlePasteSpecialDialog::m_ps](#m_ps)|Türü yapısını **OLEUIPASTESPECIAL** iletişim kutusunun işlevi denetler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıfın bir nesnesi oluşturma `COlePasteSpecialDialog` bu iletişim kutusunu çağırmak istediğinizde. Sonra bir `COlePasteSpecialDialog` nesne oluşturulan, kullanabileceğiniz [AddFormat](#addformat) ve [AddStandardFormats](#addstandardformats) Pano biçimleri Ekle iletişim kutusu için üye işlevleri. Aynı zamanda [m_ps](#m_ps) yapısı değerleri veya iletişim kutusu denetimleri durumlarını başlatılamadı. `m_ps` Yapısıdır türü **OLEUIPASTESPECIAL**.  
  
 Daha fazla bilgi için bkz: [OLEUIPASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/ms692434) Windows SDK'sındaki yapısı.  
  
 OLE özel iletişim kutuları hakkında daha fazla bilgi için bkz: [ole'deki iletişim kutuları](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COlePasteSpecialDialog`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxodlgs.h  
  
##  <a name="addformat"></a>  COlePasteSpecialDialog::AddFormat  
 Uygulamanızı bir Özel Yapıştır işleminde destekleyebilir biçimlerinin listesini yeni biçimleri eklemek için bu işlevini çağırın.  
  
```  
void AddFormat(
    const FORMATETC& formatEtc,  
    LPTSTR lpszFormat,  
    LPTSTR lpszResult,  
    DWORD flags);

 
void AddFormat(
    UINT cf,  
    DWORD tymed,  
    UINT nFormatID,  
    BOOL bEnableIcon,  
    BOOL bLink);
```  
  
### <a name="parameters"></a>Parametreler  
 *FMT*  
 Eklemek için veri türü referansı.  
  
 `lpszFormat`  
 Kullanıcı biçimine açıklayan dize.  
  
 *lpszResult*  
 Bu biçim iletişim kutusunda seçilirse sonucu açıklayan dize.  
  
 `flags`  
 Farklı bağlama ve katıştırma seçeneklerini Bu biçim için kullanılabilir. Bu bayrak bir veya daha fazla farklı değerlerin Bitsel bir birleşimi olan **OLEUIPASTEFLAG** numaralandırılmış türü.  
  
 `cf`  
 Eklemek için Pano biçimi.  
  
 *ortam türü*  
 Bu biçimde kullanılabilen medya türleri. Bir veya daha fazla değerlerin Bitsel bir birleşimi budur **ortam türü** numaralandırılmış türü.  
  
 `nFormatID`  
 Bu biçim tanımlayan dize kimliği. Bu dize bir '\n' karakteriyle ayrılmış iki ayrı dizeleri biçimidir. İlk olarak aktarılabilecek aynı dizedir *lpstrFormat* parametresi, ikincisi ise aynı *lpstrResult* parametresi.  
  
 *bEnableIcon*  
 Bu biçim liste kutusunda seçildiğinde simge olarak görüntüle onay kutusunun etkinleştirilip etkinleştirilmediğini belirleyen bayrak.  
  
 *bLink*  
 Bu biçim liste kutusunda seçildiğinde Bağlantı Yapıştır radyo düğmesi etkin olup olmadığını belirleyen bayrak.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev ya da standart biçimleri gibi eklemek için çağrılabilir **CF_TEXT** veya **CF_TIFF** ya da uygulamanızı sistemle kayıtlı olan özel biçimleri. Uygulamanıza veri nesneleri yapıştırma hakkında daha fazla bilgi için bkz: [veri nesneleri ve veri kaynakları: düzenleme](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Daha fazla bilgi için bkz: [ortam türü](http://msdn.microsoft.com/library/windows/desktop/ms691227) numaralandırma türü ve [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki yapısı.  
  
 Daha fazla bilgi için bkz: [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) numaralandırılmış Windows SDK'sındaki türü.  
  
##  <a name="addlinkentry"></a>  COlePasteSpecialDialog::AddLinkEntry  
 Yeni bir giriş desteklenen Pano biçimleri listesine ekler.  
  
```  
OLEUIPASTEFLAG AddLinkEntry(UINT cf);
```  
  
### <a name="parameters"></a>Parametreler  
 `cf`  
 Eklemek için Pano biçimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) yeni bağlantı giriş bilgilerini içeren yapısı.  
  
##  <a name="addstandardformats"></a>  COlePasteSpecialDialog::AddStandardFormats  
 Uygulamanızı bir Özel Yapıştır işleminde destekleyebilir biçimlerinin listesini aşağıdaki Pano biçimlerini eklemek için bu işlevini çağırın:  
  
```  
void AddStandardFormats(BOOL bEnableLink = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *bEnableLink*  
 Eklenip eklenmeyeceğini belirleyen bayrak `CF_LINKSOURCE` biçimlerinin listesi için uygulamanızın yapıştırabilirsiniz.  
  
### <a name="remarks"></a>Açıklamalar  
  
- **CF_BITMAP**  
  
- **CF_DIB**  
  
- `CF_METAFILEPICT`  
  
- **"Katıştırılmış nesne"**  
  
-   (isteğe bağlı) **"Bağlantı kaynak"**  
  
 Bu biçimler katıştırma ve bağlama desteklemek için kullanılır.  
  
##  <a name="colepastespecialdialog"></a>  COlePasteSpecialDialog::COlePasteSpecialDialog  
 Oluşturan bir `COlePasteSpecialDialog` nesnesi.  
  
```  
COlePasteSpecialDialog(
    DWORD dwFlags = PSF_SELECTPASTE,  
    COleDataObject* pDataObject = NULL,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwFlags`  
 Bit düzeyinde OR işleci kullanılarak birleştirilen aşağıdaki bayraklar herhangi bir sayıda oluşturma bayrağı içerir:  
  
- `PSF_SELECTPASTE` İletişim kutusu çağrıldığında, Yapıştır radyo düğmesi'nin başlangıçta kontrol edileceği belirtir. İle birlikte kullanılamaz `PSF_SELECTPASTELINK`. Bu varsayılandır.  
  
- `PSF_SELECTPASTELINK` İletişim kutusu ne zaman çağrıldığını radyo düğmesi olacaktır Yapıştır başlangıçta işaretli belirtir. İle birlikte kullanılamaz `PSF_SELECTPASTE`.  
  
- `PSF_CHECKDISPLAYASICON` İletişim kutusu çağrıldığında, simge olarak görüntüle onay kutusunun'in başlangıçta kontrol edileceği belirtir.  
  
- `PSF_SHOWHELP` İletişim kutusu çağrıldığında Yardım düğmesi görüntülenir belirtir.  
  
 `pDataObject`  
 İşaret [COleDataObject](../../mfc/reference/coledataobject-class.md) yapıştırma. Bu değer ise **NULL**, alır `COleDataObject` panodan.  
  
 `pParentWnd`  
 İşaret üst veya sahibi pencere nesnesi için (tür `CWnd`) iletişim nesnesi ait olduğu. Eğer öyleyse **NULL**, iletişim kutusunun üst pencere ana uygulama penceresine ayarlanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev yalnızca oluşturan bir `COlePasteSpecialDialog` nesnesi. İletişim kutusunu görüntülemek için arama [DoModal](#domodal) işlevi.  
  
 Daha fazla bilgi için bkz: [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) numaralandırılmış Windows SDK'sındaki türü.  
  
##  <a name="createitem"></a>  COlePasteSpecialDialog::CreateItem  
 Özel Yapıştır iletişim kutusunda seçildi yeni öğesi oluşturur.  
  
```  
BOOL CreateItem(COleClientItem* pNewItem);
```  
  
### <a name="parameters"></a>Parametreler  
 *pNewItem*  
 İşaret eden bir `COleClientItem` örneği. Olamaz **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe başarıyla oluşturulduysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev yalnızca sonra çağrılmalıdır [DoModal](#domodal) döndürür **IDOK**.  
  
##  <a name="domodal"></a>  COlePasteSpecialDialog::DoModal  
 OLE Özel Yapıştır iletişim kutusunu görüntüler.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tamamlanma durumu iletişim kutusu için. Aşağıdaki değerlerden biri:  
  
- **IDOK** iletişim kutusu başarıyla görüntüleniyorsa.  
  
- **IDCANCEL** kullanıcı iletişim kutusunu iptal ederseniz.  
  
- **IDABORT** durumunda bir hata oluştu. Varsa **IDABORT** olan döndürülen arama `COleDialog::GetLastError` oluştu hata türü hakkında daha fazla bilgi almak için üye işlevi. Olası hatalar listesi için bkz: [OleUIPasteSpecial](http://msdn.microsoft.com/library/windows/desktop/ms694512) Windows SDK'sındaki işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Üyeleri ayarlayarak çeşitli iletişim kutusu denetimleri başlatmak istiyorsanız [m_ps](#m_ps) yapısı, bu çağırmadan önce yapmanız gerektiğini `DoModal`, ancak iletişim nesnesi oluşturulur.  
  
 Varsa `DoModal` döndürür **IDOK**, diğer üye ayarları veya kullanıcı tarafından bilgi giriş iletişim kutusuna almak için işlevleri çağırabilir.  
  
##  <a name="getdrawaspect"></a>  COlePasteSpecialDialog::GetDrawAspect  
 Seçilen öğe bir simge olarak görüntülemek kullanıcı seçerseniz belirler.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesneyi işlemek için gerekli yöntemi.  
  
- `DVASPECT_CONTENT` İletişim kutusu kapatıldığında simge olarak görüntüle onay kutusunun işaretli değil, döndürdü.  
  
- `DVASPECT_ICON` İletişim kutusu kapatıldığında simge olarak göster onay kutusu işaretli değilse döndürdü.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca sonra bu işlevi çağırmak [DoModal](#domodal) döndürür **IDOK**.  
  
 En boy çizim daha fazla bilgi için bkz: [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki yapısı.  
  
##  <a name="geticonicmetafile"></a>  COlePasteSpecialDialog::GetIconicMetafile  
 Kullanıcı tarafından seçilen öğeyle ilişkili meta dosyası alır.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçilen öğenin simge en boy simge olarak göster onay kutusunu seçerek iletişim kutusu kapatıldığında seçtiyseniz içeren meta dosyası tanıtıcısını **Tamam**; Aksi halde **NULL**.  
  
##  <a name="getpasteindex"></a>  COlePasteSpecialDialog::GetPasteIndex  
 Alır dizin değeri seçili kullanıcı girişiyle ilişkili.  
  
```  
int GetPasteIndex() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizi dizine **OLEUIPASTEENTRY** kullanıcı tarafından seçilen yapıları. Seçili dizine karşılık gelen biçimi yapıştırma işlemi gerçekleştirirken kullanılmalıdır.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [OLEUIPASTEENTRY](http://msdn.microsoft.com/library/windows/desktop/ms690165) Windows SDK'sındaki yapısı.  
  
##  <a name="getselectiontype"></a>  COlePasteSpecialDialog::GetSelectionType  
 Kullanıcı yapılan seçim türünü belirler.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yapılan seçim türünü döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından belirtilen dönüş türü değerleri **seçimi** numaralandırma türü içinde bildirilen `COlePasteSpecialDialog` sınıfı.  
  
```  
enum Selection {
    pasteLink,
    pasteNormal,
    pasteOther,
    pasteStatic
    };  
```  
  
 Bu değerlerin kısa desccriptions izleyin:  
  
- **COlePasteSpecialDialog::pasteLink** Bağlantı Yapıştır radyo düğmesi işaretlendiğinde ve seçilen biçimi standart bir OLE biçim olduğundan.  
  
- **COlePasteSpecialDialog::pasteNormal** Yapıştır radyo düğmesi işaretlendiğinde ve seçilen biçimi standart bir OLE biçim oluştu.  
  
- **COlePasteSpecialDialog::pasteOther** seçilen biçiminde standart OLE biçiminde değil.  
  
- **COlePasteSpecialDialog::pasteStatic** seçilen biçimi meta dosyası oluştu.  
  
##  <a name="m_ps"></a>  COlePasteSpecialDialog::m_ps  
 Türü yapısını **OLEUIPASTESPECIAL** Özel Yapıştır iletişim kutusu davranışını denetlemek için kullanılır.  
  
```  
OLEUIPASTESPECIAL m_ps;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yapı üyeleri, doğrudan veya üye işlevleri aracılığıyla değiştirilebilir.  
  
 Daha fazla bilgi için bkz: [OLEUIPASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/ms692434) Windows SDK'sındaki yapısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek OCLIENT](../../visual-cpp-samples.md)   
 [COleDialog sınıfı](../../mfc/reference/coledialog-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
