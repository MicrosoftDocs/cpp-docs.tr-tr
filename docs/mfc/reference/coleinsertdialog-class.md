---
title: "COleInsertDialog sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleInsertDialog
- AFXODLGS/COleInsertDialog
- AFXODLGS/COleInsertDialog::COleInsertDialog
- AFXODLGS/COleInsertDialog::CreateItem
- AFXODLGS/COleInsertDialog::DoModal
- AFXODLGS/COleInsertDialog::GetClassID
- AFXODLGS/COleInsertDialog::GetDrawAspect
- AFXODLGS/COleInsertDialog::GetIconicMetafile
- AFXODLGS/COleInsertDialog::GetPathName
- AFXODLGS/COleInsertDialog::GetSelectionType
- AFXODLGS/COleInsertDialog::m_io
dev_langs:
- C++
helpviewer_keywords:
- COleInsertDialog [MFC], COleInsertDialog
- COleInsertDialog [MFC], CreateItem
- COleInsertDialog [MFC], DoModal
- COleInsertDialog [MFC], GetClassID
- COleInsertDialog [MFC], GetDrawAspect
- COleInsertDialog [MFC], GetIconicMetafile
- COleInsertDialog [MFC], GetPathName
- COleInsertDialog [MFC], GetSelectionType
- COleInsertDialog [MFC], m_io
ms.assetid: a9ec610b-abde-431e-bd01-c40159a66dbb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4638471ed199d08bb21bcf16465fe933af3a584c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="coleinsertdialog-class"></a>COleInsertDialog sınıfı
OLE Nesne Ekle iletişim kutusu için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleInsertDialog : public COleDialog  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleInsertDialog::COleInsertDialog](#coleinsertdialog)|Oluşturan bir `COleInsertDialog` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleInsertDialog::CreateItem](#createitem)|İletişim kutusunda seçili öğesi oluşturur.|  
|[COleInsertDialog::DoModal](#domodal)|OLE Nesne Ekle iletişim kutusu görüntüler.|  
|[COleInsertDialog::GetClassID](#getclassid)|Alır **CLSID** Seçilen öğeyle ilişkili.|  
|[COleInsertDialog::GetDrawAspect](#getdrawaspect)|Öğesi bir simge olarak çizileceğini belirtir.|  
|[COleInsertDialog::GetIconicMetafile](#geticonicmetafile)|Bu öğe simge formla ilişkili meta dosyası için bir tanıtıcı alır.|  
|[COleInsertDialog::GetPathName](#getpathname)|İletişim kutusunda seçilen dosyanın tam yolunu alır.|  
|[COleInsertDialog::GetSelectionType](#getselectiontype)|Seçili nesne türünü alır.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleInsertDialog::m_io](#m_io)|Türü yapısını **OLEUIINSERTOBJECT** iletişim kutusu davranışını denetler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıfın bir nesnesi oluşturma `COleInsertDialog` bu iletişim kutusunu çağırmak istediğinizde. Sonra bir `COleInsertDialog` nesne oluşturulan, kullanabileceğiniz [m_io](#m_io) yapısı değerleri veya iletişim kutusu denetimleri durumlarını başlatılamadı. `m_io` Yapısıdır türü **OLEUIINSERTOBJECT**. Bu iletişim kutusu sınıfı kullanma hakkında daha fazla bilgi için bkz: [DoModal](#domodal) üye işlevi.  
  
> [!NOTE]
>  Uygulama Sihirbazı tarafından oluşturulan kapsayıcı kodu bu sınıfı kullanır.  
  
 Daha fazla bilgi için bkz: [OLEUIINSERTOBJECT](http://msdn.microsoft.com/library/windows/desktop/ms691316) Windows SDK'sındaki yapısı.  
  
 OLE özel iletişim kutuları hakkında daha fazla bilgi için bkz: [ole'deki iletişim kutuları](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleInsertDialog`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxodlgs.h  
  
##  <a name="coleinsertdialog"></a>COleInsertDialog::COleInsertDialog  
 Bu işlev yalnızca oluşturan bir `COleInsertDialog` nesnesi.  
  
```  
COleInsertDialog (
    DWORD dwFlags = IOF_SELECTCREATENEW,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwFlags`  
 Bit düzeyinde OR işleci kullanılarak birleştirilen için aşağıdaki değerleri herhangi bir sayıda içeren oluşturma bayrağı:  
  
- **IOF_SHOWHELP** iletişim kutusu çağrıldığında Yardım düğmesi görüntülenir belirtir.  
  
- **IOF_SELECTCREATENEW** iletişim kutusu çağrıldığında, Yeni Oluştur radyo düğmesi'nin başlangıçta seçili olur belirtir. Bu varsayılandır ve kullanılamaz **IOF_SELECTCREATEFROMFILE**.  
  
- **IOF_SELECTCREATEFROMFILE** iletişim kutusu çağrıldığında, Dosyadan Oluştur radyo düğmesi'nin başlangıçta seçili olur belirtir. Kullanılamaz **IOF_SELECTCREATENEW**.  
  
- **IOF_CHECKLINK** iletişim kutusu çağrıldığında, bağlantı onay kutusunu'nin başlangıçta kontrol edileceği belirtir.  
  
- **IOF_DISABLELINK** iletişim kutusu çağrıldığında bağlantı onay kutusunu devre dışı bırakılacak belirtir.  
  
- **IOF_CHECKDISPLAYASICON** simge olarak görüntüle onay kutusunun başlangıçta denetlenir, geçerli simgesi görüntülenir ve iletişim kutusunu çağrıldığında Simge Değiştir düğmesi etkinleştirilir belirtir.  
  
- **IOF_VERIFYSERVERSEXIST** iletişim kutusu görüntülenmeden önce kayıt veritabanında belirtilen sunucular mevcut sağlayarak liste kutusu ekler sınıfları Doğrula iletişim kutusu belirtir. Bu bayrak olarak ayarlandığında, önemli ölçüde performans zarar verebilir.  
  
 `pParentWnd`  
 İşaret üst veya sahibi pencere nesnesi için (tür `CWnd`) iletişim nesnesi ait olduğu. Eğer öyleyse **NULL**, iletişim nesnenin üst pencere ana uygulama penceresine ayarlanır.  
  
### <a name="remarks"></a>Açıklamalar  
 İletişim kutusunu görüntülemek için arama [DoModal](#domodal) işlevi.  
  
##  <a name="createitem"></a>COleInsertDialog::CreateItem  
 Türünde bir nesne oluşturmak için bu işlevi çağırmak [COleClientItem](../../mfc/reference/coleclientitem-class.md) yalnızca [DoModal](#domodal) döndürür **IDOK**.  
  
```  
BOOL CreateItem(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>Parametreler  
 `pItem`  
 Oluşturulacak öğesine noktaları.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe oluşturduysanız sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Tahsis etmelisiniz `COleClientItem` bu işlevi çağırmak önce nesne.  
  
##  <a name="domodal"></a>COleInsertDialog::DoModal  
 OLE Nesne Ekle iletişim kutusunu görüntülemek için bu işlevini çağırın.  
  
```  
virtual INT_PTR   
    DoModal();

 
INT_PTR   
    DoModal(DWORD  dwFlags);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwFlags`  
 Aşağıdaki değerlerden biri:  
  
 `COleInsertDialog::DocObjectsOnly`yalnızca DocObjects ekler.  
  
 `COleInsertDialog::ControlsOnly`Yalnızca ActiveX denetimlerini ekler.  
  
 Sıfır DocObject ne bir ActiveX denetimini ekler. Bu değer ilk prototip olarak aynı uygulaması sonuçlarında, yukarıda listelenen.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tamamlanma durumu iletişim kutusu için. Aşağıdaki değerlerden biri:  
  
-   İletişim kutusu başarıyla görüntülendiyse IDOK.  
  
-   IDCANCEL kullanıcı iletişim kutusunu iptal etti.  
  
-   IDABORT bir hata oluştu. IDABORT döndürülürse, çağrı [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) oluştu hata türü hakkında daha fazla bilgi almak için üye işlevi. Olası hatalar listesi için bkz: [OleUIInsertObject](http://msdn.microsoft.com/library/windows/desktop/ms694325) Windows SDK'sındaki işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Üyeleri ayarlayarak çeşitli iletişim kutusu denetimleri başlatmak istiyorsanız [m_io](#m_io) yapısı, bu çağırmadan önce yapmanız gerektiğini `DoModal`, ancak iletişim nesnesi oluşturulur.  
  
 Varsa `DoModal` IDOK, döndürür diğer üye ayarları veya kullanıcı tarafından iletişim kutusuna bilgi giriş almak için işlevleri çağırabilir.  
  
##  <a name="getclassid"></a>COleInsertDialog::GetClassID  
 Almak için bu işlevi çağırmak **CLSID** seçili öğe yalnızca ilişkili [DoModal](#domodal) döndürür **IDOK** ve Seçim türünü **COleInsertDialog:: createNewItem**.  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **CLSID** seçilen öğe ile ilişkili.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [CLSID anahtarı](http://msdn.microsoft.com/library/windows/desktop/ms691424) Windows SDK'sındaki.  
  
##  <a name="getdrawaspect"></a>COleInsertDialog::GetDrawAspect  
 Seçilen öğe bir simge olarak görüntülemek kullanıcı seçerseniz belirlemek için bu işlevini çağırın.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesneyi işlemek için gerekli yöntemi.  
  
- `DVASPECT_CONTENT`Simge olarak göster onay kutusu işaretli değilse döndürdü.  
  
- `DVASPECT_ICON`Simge olarak göster onay kutusu denetlendi döndürdü.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev yalnızca, çağrı [DoModal](#domodal) döndürür **IDOK**.  
  
 En boy çizim daha fazla bilgi için bkz: [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki veri yapısı.  
  
##  <a name="geticonicmetafile"></a>COleInsertDialog::GetIconicMetafile  
 Seçilen öğenin simge en boy içeren meta dosyası için bir tanıtıcı almak için bu işlevini çağırın.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İletişim kutusu seçerek zaman kapatıldığında simge olarak göster onay kutusu ise, simge en boy seçilen öğenin içeren meta dosyası tanıtıcısını işaretli **Tamam**; Aksi halde **NULL**.  
  
##  <a name="getpathname"></a>COleInsertDialog::GetPathName  
 Seçilen dosya eksikse tam yolunu almak için bu işlevi çağırmak [DoModal](#domodal) döndürür **IDOK** ve Seçim türünü değil **COleInsertDialog::createNewItem**.  
  
```  
CString GetPathName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İletişim kutusunda seçili dosyasının tam yolu. Seçim türünü ise `createNewItem`, bu işlev bir anlamsız döndürür `CString` yayın modunda veya bir onaylama hata ayıklama modunda neden olur.  
  
##  <a name="getselectiontype"></a>COleInsertDialog::GetSelectionType  
 Nesne Ekle iletişim kutusu seçerek zaman kapatıldığında seçilen seçim türünü almak için bu işlevi çağırmak **Tamam**.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yapılan seçim türü.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından belirtilen dönüş türü değerleri **seçimi** numaralandırma türü içinde bildirilen `COleInsertDialog` sınıfı.  
  
```  
enum Selection {
    createNewItem,
    insertFromFile,
    linkToFile
    };  
```  
  
 Bu değerlerin kısa açıklamaları izleyin:  
  
- **COleInsertDialog::createNewItem** Yeni Oluştur radyo düğmesi seçilmedi.  
  
- **COleInsertDialog::insertFromFile** Dosyadan Oluştur radyo düğmesi seçildiğinde ve bağlantı onay kutusunun işaretlenmemiş.  
  
- **COleInsertDialog::linkToFile** Dosyadan Oluştur radyo düğmesi seçildiğinde ve bağlantı onay kutusunu denetlendi.  
  
##  <a name="m_io"></a>COleInsertDialog::m_io  
 Türü yapısını **OLEUIINSERTOBJECT** Nesne Ekle iletişim kutusu davranışını denetlemek için kullanılır.  
  
```  
OLEUIINSERTOBJECT m_io;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yapı üyeleri, doğrudan ya da üye işlevleri üzerinden değiştirilebilir.  
  
 Daha fazla bilgi için bkz: [OLEUIINSERTOBJECT](http://msdn.microsoft.com/library/windows/desktop/ms691316) Windows SDK'sındaki yapısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek OCLIENT](../../visual-cpp-samples.md)   
 [COleDialog sınıfı](../../mfc/reference/coledialog-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
