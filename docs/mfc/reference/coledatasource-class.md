---
title: COleDataSource sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDataSource
- AFXOLE/COleDataSource
- AFXOLE/COleDataSource::COleDataSource
- AFXOLE/COleDataSource::CacheData
- AFXOLE/COleDataSource::CacheGlobalData
- AFXOLE/COleDataSource::DelayRenderData
- AFXOLE/COleDataSource::DelayRenderFileData
- AFXOLE/COleDataSource::DelaySetData
- AFXOLE/COleDataSource::DoDragDrop
- AFXOLE/COleDataSource::Empty
- AFXOLE/COleDataSource::FlushClipboard
- AFXOLE/COleDataSource::GetClipboardOwner
- AFXOLE/COleDataSource::OnRenderData
- AFXOLE/COleDataSource::OnRenderFileData
- AFXOLE/COleDataSource::OnRenderGlobalData
- AFXOLE/COleDataSource::OnSetData
- AFXOLE/COleDataSource::SetClipboard
dev_langs:
- C++
helpviewer_keywords:
- COleDataSource [MFC], COleDataSource
- COleDataSource [MFC], CacheData
- COleDataSource [MFC], CacheGlobalData
- COleDataSource [MFC], DelayRenderData
- COleDataSource [MFC], DelayRenderFileData
- COleDataSource [MFC], DelaySetData
- COleDataSource [MFC], DoDragDrop
- COleDataSource [MFC], Empty
- COleDataSource [MFC], FlushClipboard
- COleDataSource [MFC], GetClipboardOwner
- COleDataSource [MFC], OnRenderData
- COleDataSource [MFC], OnRenderFileData
- COleDataSource [MFC], OnRenderGlobalData
- COleDataSource [MFC], OnSetData
- COleDataSource [MFC], SetClipboard
ms.assetid: 02c8ee7d-8e10-4463-8613-bb2a0305ca69
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4df2584bd9b74640266d8ddf87087e2820deaac8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="coledatasource-class"></a>COleDataSource sınıfı
İçine bir uygulama veri sırasında sunacaktır veri yerleştirir bir önbellek görür Pano ya da sürükle ve bırak işlemleri gibi işlemleri aktarın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleDataSource : public CCmdTarget  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDataSource::COleDataSource](#coledatasource)|Oluşturan bir `COleDataSource` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDataSource::CacheData](#cachedata)|Belirtilen biçimi kullanarak verileri sunar bir **STGMEDIUM** yapısı.|  
|[COleDataSource::CacheGlobalData](#cacheglobaldata)|Belirtilen biçimi kullanarak verileri sunar bir `HGLOBAL`.|  
|[COleDataSource::DelayRenderData](#delayrenderdata)|Gecikmeli işleme kullanarak belirtilen biçimde verisi sunar.|  
|[COleDataSource::DelayRenderFileData](#delayrenderfiledata)|Belirtilen bir biçimde verilerde sunar bir `CFile` işaretçi.|  
|[COleDataSource::DelaySetData](#delaysetdata)|Desteklenen her biçim için adlı `OnSetData`.|  
|[COleDataSource::DoDragDrop](#dodragdrop)|Bir veri kaynağı ile sürükle ve bırak işlemleri gerçekleştirir.|  
|[COleDataSource::Empty](#empty)|Boşaltır `COleDataSource` veri nesnesi.|  
|[COleDataSource::FlushClipboard](#flushclipboard)|Tüm verileri Pano'ya işler.|  
|[COleDataSource::GetClipboardOwner](#getclipboardowner)|Pano'ya yerleştirilen veriler hala var olduğunu doğrular.|  
|[COleDataSource::OnRenderData](#onrenderdata)|Gecikmeli işleme bir parçası olarak verileri alır.|  
|[COleDataSource::OnRenderFileData](#onrenderfiledata)|Verileri alır bir `CFile` Gecikmeli işleme bir parçası olarak.|  
|[COleDataSource::OnRenderGlobalData](#onrenderglobaldata)|Verileri alır bir `HGLOBAL` Gecikmeli işleme bir parçası olarak.|  
|[COleDataSource::OnSetData](#onsetdata)|Verileri değiştirme için çağrılır `COleDataSource` nesnesi.|  
|[COleDataSource::SetClipboard](#setclipboard)|Basamak bir `COleDataSource` Pano nesnesinde.|  
  
## <a name="remarks"></a>Açıklamalar  
 OLE veri kaynaklarını doğrudan oluşturabilirsiniz. Alternatif olarak, [COleClientItem](../../mfc/reference/coleclientitem-class.md) ve [COleServerItem](../../mfc/reference/coleserveritem-class.md) sınıfları yanıt olarak OLE veri kaynakları oluşturma kendi `CopyToClipboard` ve `DoDragDrop` üye işlevleri. Bkz: [COleServerItem::CopyToClipboard](../../mfc/reference/coleserveritem-class.md#copytoclipboard) kısa bir açıklama için. Geçersiz kılma `OnGetClipboardData` sınıfının üye işlevini ek Pano biçimleri OLE veri kaynağındaki verileri eklemek için istemci öğesi veya sunucu öğesi oluşturulan `CopyToClipboard` veya `DoDragDrop` üye işlevi.  
  
 Veri aktarımı için hazırlamak istediğinizde, bu sınıfın bir nesnesi oluşturma ve verileriniz için en uygun yöntemi kullanarak verilerinizi ile doldurun. Bir veri kaynağına eklenir yolu olup verileri hemen sağlanır tarafından doğrudan etkilenen (anlık görüntü oluşturma) veya isteğe bağlı (Gecikmeli işleme). İçinde sağlayan veri kullanılacak Pano biçimi geçirerek her Pano biçimi için (ve isteğe bağlı bir [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) yapısı), çağrı [DelayRenderData](#delayrenderdata).  
  
 Veri kaynakları ve veri aktarımı hakkında daha fazla bilgi için bkz: [veri nesneleri ve veri kaynakları (OLE)](../../mfc/data-objects-and-data-sources-ole.md). Ayrıca, makaleyi [Pano konuları](../../mfc/clipboard.md) OLE Pano mekanizmasını açıklar.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDataSource`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxole.h  
  
##  <a name="cachedata"></a>  COleDataSource::CacheData  
 Veri aktarım işlemleri sırasında veri sunulur biçimini belirtmek için bu işlevini çağırın.  
  
```  
void CacheData(
    CLIPFORMAT cfFormat,  
    LPSTGMEDIUM lpStgMedium,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `cfFormat`  
 Veri sunulmasına olduğu Pano biçimi. Bu parametre bir ön tanımlı Pano biçimleri veya yerel Windows tarafından döndürülen değer olabilir [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) işlevi.  
  
 `lpStgMedium`  
 İşaret eden bir [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) belirtilen biçimde verileri içeren yapısı.  
  
 `lpFormatEtc`  
 İşaret eden bir [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) veri olduğu sunulmasına biçimi açıklayan yapısı. Pano biçimi tarafından belirtilen ötesinde ek biçim bilgilerini belirtmek istiyorsanız, bu parametre için bir değer sağlayın `cfFormat`. Eğer öyleyse **NULL**, diğer alanları için varsayılan değerler kullanılır **FORMATETC** yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, hemen işleme kullanarak sağladığından verileri sağlamanız gerekir. Verileri gerektiği kadar önbelleğe alınır.  
  
 Kullanarak veri kaynağı bir [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) yapısı. Aynı zamanda `CacheGlobalData` veri miktarını sağlamış olursunuz, üye işlevi verimli şekilde kullanma aktarılması için küçük bir `HGLOBAL`.  
  
 Çağrısından sonra `CacheData` **ptd** üyesi `lpFormatEtc` ve içeriğini `lpStgMedium` çağıran tarafından veri nesnesi tarafından sahip olunan.  
  
 Gecikmeli işleme kullanmak için arama [DelayRenderData](#delayrenderdata) veya [DelayRenderFileData](#delayrenderfiledata) üye işlevi. MFC tarafından işlenmiş olarak hakkında daha fazla bilgi için Gecikmeli işleme makalesine bakın [veri nesneleri ve veri kaynakları: düzenleme](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Daha fazla bilgi için bkz: [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) ve [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) yapıları Windows SDK.  
  
 Daha fazla bilgi için bkz: [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Windows SDK'sındaki.  
  
##  <a name="cacheglobaldata"></a>  COleDataSource::CacheGlobalData  
 Veri aktarım işlemleri sırasında veri sunulur biçimini belirtmek için bu işlevini çağırın.  
  
```  
void CacheGlobalData(
    CLIPFORMAT cfFormat,  
    HGLOBAL hGlobal,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `cfFormat`  
 Veri sunulmasına olduğu Pano biçimi. Bu parametre bir ön tanımlı Pano biçimleri veya yerel Windows tarafından döndürülen değer olabilir [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) işlevi.  
  
 *hGlobal*  
 Belirtilen biçim verileri içeren genel bellek bloğu için işleyin.  
  
 `lpFormatEtc`  
 İşaret eden bir [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) veri olduğu sunulmasına biçimi açıklayan yapısı. Pano biçimi tarafından belirtilen ötesinde ek biçim bilgilerini belirtmek istiyorsanız, bu parametre için bir değer sağlayın `cfFormat`. Eğer öyleyse **NULL**, diğer alanları için varsayılan değerler kullanılır **FORMATETC** yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev hemen işleme, veri işlevi çağırırken sağlamalısınız şekilde kullanarak veri sağlar; verileri gerektiği kadar önbelleğe alınır. Kullanım `CacheData` büyük miktarda veri veya yapılandırılmış depolama ortamına gerektirip gerektirmediğini sağlamış olursunuz, üye işlevi.  
  
 Gecikmeli işleme kullanmak için arama [DelayRenderData](#delayrenderdata) veya [DelayRenderFileData](#delayrenderfiledata) üye işlevi. MFC tarafından işlenmiş olarak hakkında daha fazla bilgi için Gecikmeli işleme makalesine bakın [veri nesneleri ve veri kaynakları: düzenleme](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Daha fazla bilgi için bkz: [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki yapısı.  
  
 Daha fazla bilgi için bkz: [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Windows SDK'sındaki.  
  
##  <a name="coledatasource"></a>  COleDataSource::COleDataSource  
 Oluşturan bir `COleDataSource` nesnesi.  
  
```  
COleDataSource();
```  
  
##  <a name="delayrenderdata"></a>  COleDataSource::DelayRenderData  
 Veri aktarım işlemleri sırasında veri sunulur biçimini belirtmek için bu işlevini çağırın.  
  
```  
void DelayRenderData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `cfFormat`  
 Veri sunulmasına olduğu Pano biçimi. Bu parametre bir ön tanımlı Pano biçimleri veya yerel Windows tarafından döndürülen değer olabilir [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) işlevi.  
  
 `lpFormatEtc`  
 İşaret eden bir [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) veri olduğu sunulmasına biçimi açıklayan yapısı. Pano biçimi tarafından belirtilen ötesinde ek biçim bilgilerini belirtmek istiyorsanız, bu parametre için bir değer sağlayın `cfFormat`. Eğer öyleyse **NULL**, diğer alanları için varsayılan değerler kullanılır **FORMATETC** yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev Gecikmeli işleme, veri hemen sağlanmayan şekilde kullanarak veri sağlar. [OnRenderData](#onrenderdata) veya [OnRenderGlobalData](#onrenderglobaldata) üye işlevi veri istemek için çağrılır.  
  
 Verilerinizi aracılığıyla sağlamak için yapmayacağınız bu işlevi kullanın bir `CFile` nesnesi. Üzerinden veri sağlamak için kullanacaksanız bir `CFile` nesne, çağrı [DelayRenderFileData](#delayrenderfiledata) üye işlevi. MFC tarafından işlenmiş olarak hakkında daha fazla bilgi için Gecikmeli işleme makalesine bakın [veri nesneleri ve veri kaynakları: düzenleme](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Hemen işleme kullanmak için arama [CacheData](#cachedata) veya [CacheGlobalData](#cacheglobaldata) üye işlevi.  
  
 Daha fazla bilgi için bkz: [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki yapısı.  
  
 Daha fazla bilgi için bkz: [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Windows SDK'sındaki.  
  
##  <a name="delayrenderfiledata"></a>  COleDataSource::DelayRenderFileData  
 Veri aktarım işlemleri sırasında veri sunulur biçimini belirtmek için bu işlevini çağırın.  
  
```  
void DelayRenderFileData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `cfFormat`  
 Veri sunulmasına olduğu Pano biçimi. Bu parametre bir ön tanımlı Pano biçimleri veya yerel Windows tarafından döndürülen değer olabilir [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) işlevi.  
  
 `lpFormatEtc`  
 İşaret eden bir [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) veri olduğu sunulmasına biçimi açıklayan yapısı. Pano biçimi tarafından belirtilen ötesinde ek biçim bilgilerini belirtmek istiyorsanız, bu parametre için bir değer sağlayın `cfFormat`. Eğer öyleyse **NULL**, diğer alanları için varsayılan değerler kullanılır **FORMATETC** yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev Gecikmeli işleme, veri hemen sağlanmayan şekilde kullanarak veri sağlar. [OnRenderFileData](#onrenderfiledata) üye işlevi veri istemek için çağrılır.  
  
 Kullanmak için kullanacaksanız bu işlevi kullanın bir `CFile` veri sağlamak için nesne. Kullanılacak yapmayacağınız varsa bir `CFile` nesne, çağrı [DelayRenderData](#delayrenderdata) üye işlevi. MFC tarafından işlenmiş olarak hakkında daha fazla bilgi için Gecikmeli işleme makalesine bakın [veri nesneleri ve veri kaynakları: düzenleme](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Hemen işleme kullanmak için arama [CacheData](#cachedata) veya [CacheGlobalData](#cacheglobaldata) üye işlevi.  
  
 Daha fazla bilgi için bkz: [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki yapısı.  
  
 Daha fazla bilgi için bkz: [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Windows SDK'sındaki.  
  
##  <a name="delaysetdata"></a>  COleDataSource::DelaySetData  
 Veri kaynağı içeriğini değiştirme desteklemek için bu işlevini çağırın.  
  
```  
void DelaySetData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `cfFormat`  
 Veri yerleştirilecek olduğu Pano biçimi. Bu parametre bir ön tanımlı Pano biçimleri veya yerel Windows tarafından döndürülen değer olabilir [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) işlevi.  
  
 `lpFormatEtc`  
 İşaret eden bir [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) veri olduğu değiştirilecek biçimi açıklayan yapısı. Pano biçimi tarafından belirtilen ötesinde ek biçim bilgilerini belirtmek istiyorsanız, bu parametre için bir değer sağlayın `cfFormat`. Eğer öyleyse **NULL**, diğer alanları için varsayılan değerler kullanılır **FORMATETC** yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 [OnSetData](#onsetdata) bu durumda çerçevesi tarafından çağrılır. Veri kaynağından framework geri döndüğünde bu yalnızca kullanılır [COleServerItem::GetDataSource](../../mfc/reference/coleserveritem-class.md#getdatasource). Varsa `DelaySetData` adlı değil, `OnSetData` işlevi hiçbir zaman çağrılır. `DelaySetData` Her bir Pano için çağrılmalıdır veya **FORMATETC** desteklediğiniz biçimi.  
  
 Daha fazla bilgi için bkz: [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki yapısı.  
  
 Daha fazla bilgi için bkz: [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Windows SDK'sındaki.  
  
##  <a name="dodragdrop"></a>  COleDataSource::DoDragDrop  
 Çağrı `DoDragDrop` bir Sürükle ve bırak işlemi bu veri kaynağı için genellikle gerçekleştirmek için üye işlevi bir [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown) işleyicisi.  
  
```  
DROPEFFECT DoDragDrop(
    DWORD dwEffects = DROPEFFECT_COPY|DROPEFFECT_MOVE|DROPEFFECT_LINK,  
    LPCRECT lpRectStartDrag = NULL,  
    COleDropSource* pDropSource = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwEffects`  
 İzin verilen sürükle ve bırak işlemleri bu veri kaynağı üzerinde. Aşağıdakilerden birini veya birkaçını olabilir:  
  
- `DROPEFFECT_COPY` Bir kopyalama işlemi gerçekleştirilebilir.  
  
- `DROPEFFECT_MOVE` Bir taşıma işlemi gerçekleştirilebilir.  
  
- `DROPEFFECT_LINK` Özgün veriler bırakılan verilerden bir bağlantı kurulamadı.  
  
- `DROPEFFECT_SCROLL` Sürükleme kaydırma işlemi oluşabilir gösterir.  
  
 `lpRectStartDrag`  
 Sürükle gerçekte başladığı tanımlar dikdörtgen işaretçi. Daha fazla bilgi için aşağıdaki Açıklamalar bölümüne bakın.  
  
 *pDropSource*  
 Bırakma kaynağı noktalarına. Varsa **NULL** sonra bir varsayılan uygulaması [COleDropSource](../../mfc/reference/coledropsource-class.md) kullanılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sürükle ve bırak işlemi tarafından oluşturulan etkin bırakma; Aksi takdirde `DROPEFFECT_NONE` sağlanan dikdörtgen ayrılmadan önce kullanıcının fare düğmesini serbest olduğundan işlemi hiçbir zaman başlıyorsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Sürükle ve bırak işlemi hemen başlamaz. Fare imlecini tarafından belirtilen dikdörtgenden bekler `lpRectStartDrag` veya milisaniye belirtilen sayıda geçtiğinde kadar. Varsa `lpRectStartDrag` olan **NULL**, dikdörtgen bir piksel boyutudur.  
  
 Gecikme süresi bir kayıt defteri anahtarı ayarı tarafından belirtilir. Çağırarak gecikme süresini değiştirebilirsiniz [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) veya [CWinApp::WriteProfileInt](../../mfc/reference/cwinapp-class.md#writeprofileint). Gecikme süresi belirtmezseniz, varsayılan değer 200 milisaniye olarak kullanılır. Sürükleme gecikme süresi şekilde depolanır:  
  
-   Windows NT Sürükle gecikme süresi içinde HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay depolanır.  
  
-   Windows 3.x Sürükle gecikme süresi WIN depolanır. INI dosyası [Windows} bölümünde.  
  
-   Windows 95/98 Sürükle gecikme süresi WIN önbelleğe alınmış bir sürümünde depolanır. INI.  
  
 Sürükleme hakkında daha fazla bilgi için gecikme bilgilerini ya da kayıt defterinde depolanır veya. INI dosyası bkz [WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504) Windows SDK'sındaki.  
  
 Daha fazla bilgi için bkz: [sürükle ve bırak: bir bırakma kaynağı uygulama](../../mfc/drag-and-drop-implementing-a-drop-source.md).  
  
##  <a name="empty"></a>  COleDataSource::Empty  
 Bu işlev boş çağırın `COleDataSource` veri nesnesi.  
  
```  
void Empty();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Her ikisi de önbelleğe ve bunlar tekrar kullanılabilmesi için gecikme işleme biçimleri boşaltılıp.  
  
 Daha fazla bilgi için bkz: [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) Windows SDK'sındaki.  
  
##  <a name="flushclipboard"></a>  COleDataSource::FlushClipboard  
 Pano'ya ve ardından uygulamanızı kapandıktan sonra Pano'dan veri yapıştırma olanak tanır verileri işler.  
  
```  
static void PASCAL FlushClipboard();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [SetClipboard](#setclipboard) verileri Pano'ya yerleştirme.  
  
##  <a name="getclipboardowner"></a>  COleDataSource::GetClipboardOwner  
 Panodaki veriler itibaren değişip değişmediğini belirleyen [SetClipboard](#setclipboard) son kez çağrıldı ve bu durumda, geçerli sahibi tanımlar.  
  
```  
static COleDataSource* PASCAL GetClipboardOwner();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Veri kaynağı şu anda Panosu'nda veya **NULL** yoksa hiçbir şey panoya veya Pano çağıran uygulama tarafından sahiplenilmedi.  
  
##  <a name="onrenderdata"></a>  COleDataSource::OnRenderData  
 Belirtilen biçim verileri almak için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpFormatEtc`  
 İşaret [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) yapısı içinde bilgi istenen biçimini belirtme.  
  
 `lpStgMedium`  
 İşaret eden bir [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) veri olduğu döndürülecek yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen biçim biridir önceden yerleştirilen `COleDataSource` kullanarak nesne [DelayRenderData](#delayrenderdata) veya [DelayRenderFileData](#delayrenderfiledata) Gecikmeli işleme için üye işlevi. Bu işlev varsayılan uygulaması çağıracak [OnRenderFileData](#onrenderfiledata) veya [OnRenderGlobalData](#onrenderglobaldata) sağlanan depolama ortamına bir dosya veya bellek, sırasıyla ise. Bu biçimler hiçbiri sağlanan durumunda varsayılan uygulaması 0 döndürür ve hiçbir şey yapma. MFC tarafından işlenmiş olarak hakkında daha fazla bilgi için Gecikmeli işleme makalesine bakın [veri nesneleri ve veri kaynakları: düzenleme](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Varsa `lpStgMedium` ->  *ortam türü* olan **TYMED_NULL**, **STGMEDIUM** tarafından belirtilen doldurulmuş ve ayrılan gerekir *lpFormatEtc -> ortam türü*. Değilse **TYMED_NULL**, **STGMEDIUM** verilerle yerinde dolu olması gerekir.  
  
 Gelişmiş budur geçersiz kılınabilir. İstenen biçim ve orta verilerinizdeki sağlamak için bu işlevi geçersiz kılar. Verilerinizi bağlı olarak, bu işlevin diğer sürümlerinden birini yerine geçersiz kılmak istediğiniz. Verilerinizi küçük ve sabit boyutu ise, geçersiz kılma `OnRenderGlobalData`. Verilerinizi bir dosyaya veya bir değişken boyutu, geçersiz kılma `OnRenderFileData`.  
  
 Daha fazla bilgi için bkz: [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) ve [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) yapıları [ortam türü](http://msdn.microsoft.com/library/windows/desktop/ms691227) numaralandırma türü ve [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) Windows SDK.  
  
##  <a name="onrenderfiledata"></a>  COleDataSource::OnRenderFileData  
 Belirtilen depolama ortamına bir dosyası olduğunda belirtilen biçiminde veri almak için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,  
    CFile* pFile);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpFormatEtc`  
 İşaret [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) yapısı içinde bilgi istenen biçimini belirtme.  
  
 `pFile`  
 İşaret eden bir [CFile](../../mfc/reference/cfile-class.md) veri olduğu işlenecek nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen biçim biridir önceden yerleştirilen `COleDataSource` kullanarak nesne [DelayRenderData](#delayrenderdata) Gecikmeli işleme için üye işlevi. Bu işlev varsayılan uygulaması yalnızca döndürür **FALSE**.  
  
 Gelişmiş budur geçersiz kılınabilir. İstenen biçim ve orta verilerinizdeki sağlamak için bu işlevi geçersiz kılar. Verilerinizi bağlı olarak, bu işlevin diğer sürümlerinden birini yerine geçersiz kılmak istediğiniz. Birden çok depolama medyası işlemek istiyorsanız, geçersiz kılma [OnRenderData](#onrenderdata). Verilerinizi bir dosyaya veya bir değişken boyutu, geçersiz kılma `OnRenderFileData`. MFC tarafından işlenmiş olarak hakkında daha fazla bilgi için Gecikmeli işleme makalesine bakın [veri nesneleri ve veri kaynakları: düzenleme](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Daha fazla bilgi için bkz: [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) yapısı ve [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) Windows SDK'sındaki.  
  
##  <a name="onrenderglobaldata"></a>  COleDataSource::OnRenderGlobalData  
 Belirtilen depolama ortamına genel bellek olduğunda belirtilen biçim verileri almak için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,  
    HGLOBAL* phGlobal);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpFormatEtc`  
 İşaret [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) yapısı içinde bilgi istenen biçimini belirtme.  
  
 `phGlobal`  
 Verileri döndürülecek olan genel bellek için bir tanıtıcı noktalarına. Bir henüz ayrıldı değil, bu parametre olabilir **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen biçim biridir önceden yerleştirilen `COleDataSource` kullanarak nesne [DelayRenderData](#delayrenderdata) Gecikmeli işleme için üye işlevi. Bu işlev varsayılan uygulaması yalnızca döndürür **FALSE**.  
  
 Varsa `phGlobal` olan **NULL**, ardından yeni `HGLOBAL` döndürdü ve ayrılan gerekir `phGlobal`. Aksi takdirde, `HGLOBAL` tarafından belirtilen `phGlobal` verilerle dolu olması gerekir. Veri miktarını yerleştirilen `HGLOBAL` bellek bloğu geçerli boyutunu aşmamalıdır. Ayrıca, büyük boyutlu bir blok ayrılamaz.  
  
 Gelişmiş budur geçersiz kılınabilir. İstenen biçim ve orta verilerinizdeki sağlamak için bu işlevi geçersiz kılar. Verilerinizi bağlı olarak, bu işlevin diğer sürümlerinden birini yerine geçersiz kılmak istediğiniz. Birden çok depolama medyası işlemek istiyorsanız, geçersiz kılma [OnRenderData](#onrenderdata). Verilerinizi bir dosyaya veya bir değişken boyutu, geçersiz kılma [OnRenderFileData](#onrenderfiledata). MFC tarafından işlenmiş olarak hakkında daha fazla bilgi için Gecikmeli işleme makalesine bakın [veri nesneleri ve veri kaynakları: düzenleme](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Daha fazla bilgi için bkz: [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) yapısı ve [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) Windows SDK'sındaki.  
  
##  <a name="onsetdata"></a>  COleDataSource::OnSetData  
 Ayarlayın veya verileri değiştirmek için framework tarafından çağrılan `COleDataSource` nesne belirtilen biçiminde.  
  
```  
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium,  
    BOOL bRelease);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpFormatEtc`  
 İşaret [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) yapısı içinde veri değiştirilir biçimini belirtme.  
  
 `lpStgMedium`  
 İşaret [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) geçerli içeriğini değiştirecek verileri içeren yapısı `COleDataSource` nesnesi.  
  
 `bRelease`  
 İşlev çağrısı tamamladıktan sonra depolama ortamına sahipliğini kimlerin olduğunu gösterir. Arayan adına depolama ortamına ayrılan kaynakları serbest bırakma için sorumlu kim karar verir. Arayan ayarlayarak bunu yapar `bRelease`. Varsa `bRelease` olduğu sıfır olmayan, veri kaynağını kullanmadan tamamlandığında Orta boşaltma, aittir. Zaman `bRelease` 0'dır, çağıran sahipliği korur ve veri kaynağı yalnızca çağrı süresince depolama ortamı kullanabilirsiniz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bunu alınırken başarıyla kadar veri kaynağının veri sahipliğini almaz. Diğer bir deyişle, sahipliği varsa almaz `OnSetData` 0 döndürür. Veri kaynağı sahipliği alırsa, çağırarak depolama ortamına boşaltır [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) işlevi.  
  
 Varsayılan uygulama hiçbir şey yapmaz. Bu işlev belirtilen biçiminde verileri değiştirmek için geçersiz kılar. Gelişmiş budur geçersiz kılınabilir.  
  
 Daha fazla bilgi için bkz: [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) ve [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) yapıları ve [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) ve [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) Windows SDK'sındaki işlevleri.  
  
##  <a name="setclipboard"></a>  COleDataSource::SetClipboard  
 Bulunan verileri koyar `COleDataSource` aşağıdaki işlevleri birini çağrıldıktan sonra Pano nesnesinde: [CacheData](#cachedata), [CacheGlobalData](#cacheglobaldata), [DelayRenderData](#delayrenderdata), veya [DelayRenderFileData](#delayrenderfiledata).  
  
```  
void SetClipboard();
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek HIERSVR](../../visual-cpp-samples.md)   
 [MFC örnek OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleDataObject Sınıfı](../../mfc/reference/coledataobject-class.md)
