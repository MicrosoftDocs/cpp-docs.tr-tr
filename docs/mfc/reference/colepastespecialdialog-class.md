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
ms.openlocfilehash: 42f4a45dc2b49b784f74175203e892c253ea1f5e
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37851439"
---
# <a name="colepastespecialdialog-class"></a>COlePasteSpecialDialog sınıfı
OLE Paste Special iletişim kutusu için kullanıldı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COlePasteSpecialDialog : public COleDialog  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COlePasteSpecialDialog::COlePasteSpecialDialog](#colepastespecialdialog)|Oluşturur bir `COlePasteSpecialDialog` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COlePasteSpecialDialog::AddFormat](#addformat)|Özel biçimler uygulamanızı yapıştırabilirsiniz biçimleri listesine ekler.|  
|[COlePasteSpecialDialog::AddLinkEntry](#addlinkentry)|Yeni bir giriş, desteklenen Pano biçimlerini listesine ekler.|  
|[COlePasteSpecialDialog::AddStandardFormats](#addstandardformats)|CF_BITMAP, CF_DIB, CF_METAFILEPICT ekler ve isteğe bağlı olarak, uygulamanızı biçimlerde listesine CF_LINKSOURCE yapıştırabilirsiniz.|  
|[COlePasteSpecialDialog::CreateItem](#createitem)|Öğesi belirtilen biçimi kullanarak kapsayıcı belgede oluşturur.|  
|[COlePasteSpecialDialog::DoModal](#domodal)|OLE Paste Special iletişim kutusu görüntüler.|  
|[COlePasteSpecialDialog::GetDrawAspect](#getdrawaspect)|Öğeyi bir simge olarak veya çizmek bu seçeneği bildirir.|  
|[COlePasteSpecialDialog::GetIconicMetafile](#geticonicmetafile)|Bu öğenin icon formla ilişkili meta dosyası için bir tanıtıcı alır.|  
|[COlePasteSpecialDialog::GetPasteIndex](#getpasteindex)|Kullanıcı tarafından seçilen kullanılabilir yapıştırma seçenekleri indisini alır.|  
|[COlePasteSpecialDialog::GetSelectionType](#getselectiontype)|Seçilen seçim türünü alır.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COlePasteSpecialDialog::m_ps](#m_ps)|İletişim kutusunun denetimlerinin OLEUIPASTESPECIAL türünden bir yapıyı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıfın bir nesnesi oluşturma `COlePasteSpecialDialog` bu iletişim kutusunu çağırmak istediğinizde. Sonra bir `COlePasteSpecialDialog` nesne oluşturulur, kullanabileceğiniz [AddFormat](#addformat) ve [AddStandardFormats](#addstandardformats) Pano biçimleri ekleme iletişim kutusuna üye işlevleri. Ayrıca [m_ps](#m_ps) yapısı değerleri veya durumları iletişim kutusundaki denetimlerin başlatılamadı. `m_ps` OLEUIPASTESPECIAL türünü yapısıdır.  
  
 Daha fazla bilgi için [OLEUIPASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/ms692434) Windows SDK'sındaki yapısı.  
  
 Özel OLE iletişim kutuları hakkında daha fazla bilgi için bkz [ole'deki iletişim kutuları](../../mfc/dialog-boxes-in-ole.md).  
  
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
 Uygulamanızı bir Özel Yapıştır işlemi destekleyebilir biçimlerinin listesini yeni biçimleri eklemek için bu işlevi çağırın.  
  
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
 Başvuru eklemek için veri türü.  
  
 *lpszFormat*  
 Kullanıcıya biçimini tanımlayan bir dize.  
  
 *lpszResult*  
 Bu biçim iletişim kutusunda seçilirse sonucu açıklayan dize.  
  
 *bayrakları*  
 Farklı bağlama ve ekleme seçenekleri için bu biçimi kullanılabilir. Bu bayrak bit düzeyinde birinin oluşur veya daha fazla farklı değerler OLEUIPASTEFLAG listelenmiş türü.  
  
 *cf*  
 Eklemek için Pano biçimi.  
  
 *ortam türü*  
 Bu biçimde kullanılabilir medya türü. Bu karşılaştırmaya bir veya daha fazla ortam türü değerleri listelenmiş türü.  
  
 *nFormatID*  
 Bu biçim tanımlayan dize kimliği. Bu dize bir '\n' karakteriyle ayrılmış iki ayrı dizeleri biçimidir. İlk olarak geçirilir aynı dizedir *lpstrFormat* parametre ve ikinci ile aynıdır *lpstrResult* parametresi.  
  
 *bEnableIcon*  
 Bu biçim liste kutusunda seçildiğinde simge olarak görüntüle onay kutusunun etkinleştirilip etkinleştirilmediğini belirleyen bayrak.  
  
 *bLink*  
 Bu biçim liste kutusunda seçildiğinde Yapıştır radyo düğmesini etkinleştirilip etkinleştirilmediğini belirleyen bayrak.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, standart biçim CF_TEXT veya CF_TIFF gibi veya özel biçimlerini uygulamanızı sistemi ile kayıtlı olan eklemek için çağrılabilir. Uygulamanıza veri nesnelerini yapıştırma hakkında daha fazla bilgi için bkz [veri nesneleri ve veri kaynakları: düzenleme](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Daha fazla bilgi için [ortam türü](http://msdn.microsoft.com/library/windows/desktop/ms691227) numaralandırma türü ve [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki yapısı.  
  
 Daha fazla bilgi için [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) listelenmiş Windows SDK'sındaki türü.  
  
##  <a name="addlinkentry"></a>  COlePasteSpecialDialog::AddLinkEntry  
 Yeni bir giriş, desteklenen Pano biçimlerini listesine ekler.  
  
```  
OLEUIPASTEFLAG AddLinkEntry(UINT cf);
```  
  
### <a name="parameters"></a>Parametreler  
 *cf*  
 Eklemek için Pano biçimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) yeni bağlantı girdinin bilgilerini içeren yapısı.  
  
##  <a name="addstandardformats"></a>  COlePasteSpecialDialog::AddStandardFormats  
 Uygulamanızı bir Özel Yapıştır işlemi destekleyebilir biçimlerinin listesini aşağıdaki Pano biçimlerini eklemek için bu işlevi çağırın:  
  
```  
void AddStandardFormats(BOOL bEnableLink = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *bEnableLink*  
 Uygulamanızı CF_LINKSOURCE biçimlerde listesine eklemek etkinleştirilip etkinleştirilmeyeceğini belirleyen bayrak yapıştırabilirsiniz.  
  
### <a name="remarks"></a>Açıklamalar  
  
- CF_BITMAP  
  
- CF_DIB  
  
- CF_METAFILEPICT  
  
- **"Katıştırılmış nesne"**  
  
-   (isteğe bağlı) **"Kaynak bağlantı"**  
  
 Bu biçimler, bağlama ve katıştırma desteklemek için kullanılır.  
  
##  <a name="colepastespecialdialog"></a>  COlePasteSpecialDialog::COlePasteSpecialDialog  
 Oluşturur bir `COlePasteSpecialDialog` nesne.  
  
```  
COlePasteSpecialDialog(
    DWORD dwFlags = PSF_SELECTPASTE,  
    COleDataObject* pDataObject = NULL,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *CertOpenStore*  
 Oluşturma bayrak bit düzeyinde OR işleci kullanılarak birleştirilen aşağıdaki bayrakları herhangi bir sayıda içerir:  
  
- Yapıştır radyo düğmesini olacak PSF_SELECTPASTE belirtir, başlangıçta iletişim kutusunu ne zaman çağrıldığını işaretli. PSF_SELECTPASTELINK ile birlikte kullanılamaz. Bu varsayılandır.  
  
- Yapıştır radyo düğmesini olacak PSF_SELECTPASTELINK belirtir, başlangıçta iletişim kutusunu ne zaman çağrıldığını işaretli. PSF_SELECTPASTE ile birlikte kullanılamaz.  
  
- Simge olarak görüntüle onay kutusunun olacak PSF_CHECKDISPLAYASICON belirtir, başlangıçta iletişim kutusunu ne zaman çağrıldığını işaretli.  
  
- PSF_SHOWHELP iletişim kutusu çağrıldığında Yardım düğmesini gösterileceğini belirtir.  
  
 *pDataObject*  
 İşaret [COleDataObject](../../mfc/reference/coledataobject-class.md) yapıştırma. Bu değer NULL ise, bunu alır `COleDataObject` panodan.  
  
 *pParentWnd*  
 Üst veya sahibi pencere nesnesi için işaret (tür `CWnd`) ait olduğu iletişim nesnesi. NULL ise, ana uygulama penceresini iletişim kutusunun üst pencere ayarlanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev yalnızca oluşturan bir `COlePasteSpecialDialog` nesne. İletişim kutusunu görüntülemek için çağrı [DoModal](#domodal) işlevi.  
  
 Daha fazla bilgi için [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) listelenmiş Windows SDK'sındaki türü.  
  
##  <a name="createitem"></a>  COlePasteSpecialDialog::CreateItem  
 Paste Special iletişim kutusunda seçilen adla yeni bir öğe oluşturur.  
  
```  
BOOL CreateItem(COleClientItem* pNewItem);
```  
  
### <a name="parameters"></a>Parametreler  
 *pNewItem*  
 İşaret eden bir `COleClientItem` örneği. NULL olamaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğesi başarıyla oluşturuldu olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev yalnızca sonra çağrılmalıdır [DoModal](#domodal) IDOK döndürür.  
  
##  <a name="domodal"></a>  COlePasteSpecialDialog::DoModal  
 OLE Paste Special iletişim kutusu görüntüler.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tamamlanma durumu iletişim kutusu için. Aşağıdaki değerlerden biri:  
  
- İletişim kutusu başarıyla görüntülendiyse IDOK.  
  
- Kullanıcı iletişim kutusunu iptal edildiyse IDCANCEL.  
  
- Bir hata oluşursa IDABORT. IDABORT döndürülürse, çağrı `COleDialog::GetLastError` konusu hatanın türü hakkında daha fazla bilgi almak için üye işlevi. Olası hataları bir listesi için bkz. [OleUIPasteSpecial](http://msdn.microsoft.com/library/windows/desktop/ms694512) Windows SDK'sında işlev.  
  
### <a name="remarks"></a>Açıklamalar  
 Çeşitli iletişim kutusu denetimleri üyeleri ayarlayarak başlatmak istiyorsanız [m_ps](#m_ps) yapısı, bunu çağırmadan önce yapmalısınız `DoModal`, ancak iletişim nesnesi oluşturulur.  
  
 Varsa `DoModal` döndürür IDOK, diğer üye işlevleri, kullanıcı giriş bilgileri ve Ayarları iletişim kutusuna alınacak çağırabilirsiniz.  
  
##  <a name="getdrawaspect"></a>  COlePasteSpecialDialog::GetDrawAspect  
 Simge olarak seçilen öğeyi görüntülemek bir kullanıcı seçerseniz belirler.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesneyi işlemek için gereken yöntem.  
  
- Simge olarak görüntüle onay kutusunun olmadıysa DVASPECT_ICON döndürülen iletişim kutusunu ne zaman sonlandırıldı teslim.  
  
- Simge olarak görüntüle onay kutusunun iletişim kutusu kapatıldığında işaretlediyseniz DVASPECT_ICON döndürdü.  
  
### <a name="remarks"></a>Açıklamalar  
 Sonra bu işlev yalnızca çağırma [DoModal](#domodal) IDOK döndürür.  
  
 En boy çizim daha fazla bilgi için bkz: [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki yapısı.  
  
##  <a name="geticonicmetafile"></a>  COlePasteSpecialDialog::GetIconicMetafile  
 Kullanıcı tarafından seçilen öğe ile ilişkili meta dosyası alır.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Simge olarak görüntüle onay kutusunu seçerek iletişim kutusu kapatıldığında seçtiyseniz seçili öğeyi icon yönüyle içeren meta tanıtıcısını **Tamam**; Aksi takdirde NULL.  
  
##  <a name="getpasteindex"></a>  COlePasteSpecialDialog::GetPasteIndex  
 Alır dizin değeri, seçilen kullanıcı girişiyle ilişkili.  
  
```  
int GetPasteIndex() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir dizi dizine `OLEUIPASTEENTRY` kullanıcı tarafından seçilen yapılar. Yapıştırma işlemi gerçekleştirirken, seçili dizine karşılık gelen biçimde kullanılmalıdır.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için [OLEUIPASTEENTRY](http://msdn.microsoft.com/library/windows/desktop/ms690165) Windows SDK'sındaki yapısı.  
  
##  <a name="getselectiontype"></a>  COlePasteSpecialDialog::GetSelectionType  
 Kullanıcının yapılan seçim türünü belirler.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yapılan seçim türü döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş türü değerleri tarafından belirtilen `Selection` numaralandırma türü içinde bildirilen `COlePasteSpecialDialog` sınıfı.  
  
```  
enum Selection {
    pasteLink,
    pasteNormal,
    pasteOther,
    pasteStatic
    };  
```  
  
 Bu değerleri kısa desccriptions izleyin:  
  
- `COlePasteSpecialDialog::pasteLink` Yapıştır radyo düğmesini denetlendi ve standart bir OLE biçimine seçili biçim idi.  
  
- `COlePasteSpecialDialog::pasteNormal` Yapıştır radyo düğmesini denetlendi ve standart bir OLE biçimine seçili biçim idi.  
  
- `COlePasteSpecialDialog::pasteOther` Seçili biçim, standart bir OLE biçiminde değil.  
  
- `COlePasteSpecialDialog::pasteStatic` Seçili biçim meta dosyası oluştu.  
  
##  <a name="m_ps"></a>  COlePasteSpecialDialog::m_ps  
 Yapı türünü OLEUIPASTESPECIAL Paste Special iletişim kutusu davranışını denetlemek için kullanılır.  
  
```  
OLEUIPASTESPECIAL m_ps;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yapının üyelerine, doğrudan ya da üye işlevleri aracılığıyla değiştirilebilir.  
  
 Daha fazla bilgi için [OLEUIPASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/ms692434) Windows SDK'sındaki yapısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek OCLIENT](../../visual-cpp-samples.md)   
 [COleDialog sınıfı](../../mfc/reference/coledialog-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
