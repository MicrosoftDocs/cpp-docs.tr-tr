---
title: COleChangeSourceDialog sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::DoModal
- AFXODLGS/COleChangeSourceDialog::GetDisplayName
- AFXODLGS/COleChangeSourceDialog::GetFileName
- AFXODLGS/COleChangeSourceDialog::GetFromPrefix
- AFXODLGS/COleChangeSourceDialog::GetItemName
- AFXODLGS/COleChangeSourceDialog::GetToPrefix
- AFXODLGS/COleChangeSourceDialog::IsValidSource
- AFXODLGS/COleChangeSourceDialog::m_cs
dev_langs:
- C++
helpviewer_keywords:
- COleChangeSourceDialog [MFC], COleChangeSourceDialog
- COleChangeSourceDialog [MFC], DoModal
- COleChangeSourceDialog [MFC], GetDisplayName
- COleChangeSourceDialog [MFC], GetFileName
- COleChangeSourceDialog [MFC], GetFromPrefix
- COleChangeSourceDialog [MFC], GetItemName
- COleChangeSourceDialog [MFC], GetToPrefix
- COleChangeSourceDialog [MFC], IsValidSource
- COleChangeSourceDialog [MFC], m_cs
ms.assetid: d0e08be7-21ef-45e1-97af-fe27d99e3bac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 376b61dbbbfe734ecc49263718902dd387c7fce8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="colechangesourcedialog-class"></a>COleChangeSourceDialog sınıfı
OLE Kaynağı Değiştir iletişim kutusu için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleChangeSourceDialog : public COleDialog  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleChangeSourceDialog::COleChangeSourceDialog](#colechangesourcedialog)|Oluşturan bir `COleChangeSourceDialog` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleChangeSourceDialog::DoModal](#domodal)|OLE Kaynağı Değiştir iletişim kutusu görüntüler.|  
|[COleChangeSourceDialog::GetDisplayName](#getdisplayname)|Tam kaynak görünen adını alır.|  
|[COleChangeSourceDialog::GetFileName](#getfilename)|Dosya adı, kaynak adından alır.|  
|[COleChangeSourceDialog::GetFromPrefix](#getfromprefix)|Önceki kaynak önekini alır.|  
|[COleChangeSourceDialog::GetItemName](#getitemname)|Öğe adı, kaynak adından alır.|  
|[COleChangeSourceDialog::GetToPrefix](#gettoprefix)|Yeni kaynak önekini alır|  
|[COleChangeSourceDialog::IsValidSource](#isvalidsource)|Kaynak geçerli olup olmadığını gösterir.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleChangeSourceDialog::m_cs](#m_cs)|İletişim kutusu davranışını denetleyen yapısı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıfın bir nesnesi oluşturma `COleChangeSourceDialog` bu iletişim kutusunu çağırmak istediğinizde. Sonra bir `COleChangeSourceDialog` nesne oluşturulan, kullanabileceğiniz [m_cs](#m_cs) yapısı değerleri veya iletişim kutusu denetimleri durumlarını başlatılamadı. `m_cs` Yapısıdır türü [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160). Bu iletişim kutusu sınıfı kullanma hakkında daha fazla bilgi için bkz: [DoModal](#domodal) üye işlevi.  
  
 Daha fazla bilgi için bkz: [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Windows SDK yapısı.  
  
 OLE özel iletişim kutuları hakkında daha fazla bilgi için bkz: [ole'deki iletişim kutuları](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeSourceDialog`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxodlgs.h  
  
##  <a name="colechangesourcedialog"></a>  COleChangeSourceDialog::COleChangeSourceDialog  
 Bu işlev oluşturan bir `COleChangeSourceDialog` nesnesi.  
  
```  
explicit COleChangeSourceDialog(
    COleClientItem* pItem,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pItem`  
 İşaretçi bağlantılı [COleClientItem](../../mfc/reference/coleclientitem-class.md) olan kaynağıdır güncelleştirilecek.  
  
 `pParentWnd`  
 İşaret üst veya sahibi pencere nesnesi için (tür `CWnd`) iletişim nesnesi ait olduğu. Eğer öyleyse **NULL**, iletişim kutusunun üst pencere ana uygulama penceresine ayarlanır.  
  
### <a name="remarks"></a>Açıklamalar  
 İletişim kutusunu görüntülemek için arama [DoModal](#domodal) işlevi.  
  
 Daha fazla bilgi için bkz: [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) yapısı ve [OleUIChangeSource](http://msdn.microsoft.com/library/windows/desktop/ms682497) Windows SDK'sındaki işlevi.  
  
##  <a name="domodal"></a>  COleChangeSourceDialog::DoModal  
 OLE Kaynağı Değiştir iletişim kutusu görüntülemek için bu işlevini çağırın.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tamamlanma durumu iletişim kutusu için. Aşağıdaki değerlerden biri:  
  
- **IDOK** iletişim kutusu başarıyla görüntüleniyorsa.  
  
- **IDCANCEL** kullanıcı iletişim kutusunu iptal ederseniz.  
  
- **IDABORT** durumunda bir hata oluştu. Varsa **IDABORT** olan döndürülen arama [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) oluştu hata türü hakkında daha fazla bilgi almak için üye işlevi. Olası hatalar listesi için bkz: [OleUIChangeSource](http://msdn.microsoft.com/library/windows/desktop/ms682497) Windows SDK'sındaki işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Üyeleri ayarlayarak çeşitli iletişim kutusu denetimleri başlatmak istiyorsanız [m_cs](#m_cs) yapısı, bu çağırmadan önce yapmanız gerektiğini `DoModal`, ancak iletişim nesnesi oluşturulur.  
  
 Varsa `DoModal` döndürür **IDOK**, üye kullanıcı tarafından girilen ayarları veya bilgileri iletişim kutusundan almak için işlevleri çağırabilir. Aşağıdaki listede tipik sorgu işlevleri adları:  
  
- [GetFileName](#getfilename)  
  
- [GetDisplayName](#getdisplayname)  
  
- [GetItemName](#getitemname)  
  
##  <a name="getdisplayname"></a>  COleChangeSourceDialog::GetDisplayName  
 Bağlı istemci öğesi için tam görünen adı almak için bu işlevini çağırın.  
  
```  
CString GetDisplayName();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tam kaynak görünen adı (ad) [COleClientItem](../../mfc/reference/coleclientitem-class.md) oluşturucuda belirtilen.  
  
##  <a name="getfilename"></a>  COleChangeSourceDialog::GetFileName  
 Bağlı istemci öğesi için görünen ad dosya ad bölümünü almak için bu işlevini çağırın.  
  
```  
CString GetFileName();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaynak görünen adı dosya ad kısmı [COleClientItem](../../mfc/reference/coleclientitem-class.md) oluşturucuda belirtilen.  
  
### <a name="remarks"></a>Açıklamalar  
 Dosya bilinen ad öğesi bilinen ad ile birlikte tam görünen adın sağlar.  
  
##  <a name="getfromprefix"></a>  COleChangeSourceDialog::GetFromPrefix  
 Önceki önek dizesi kaynağı almak için bu işlevini çağırın.  
  
```  
CString GetFromPrefix();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaynak önceki önek dizesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev yalnızca sonra çağrısı [DoModal](#domodal) döndürür **IDOK**.  
  
 Bu değer doğrudan geldiği **lpszFrom** üyesi [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) yapısı.  
  
 Daha fazla bilgi için bkz: [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Windows SDK yapısı.  
  
##  <a name="getitemname"></a>  COleChangeSourceDialog::GetItemName  
 Bağlı istemci öğesi için görünen ad öğesi ad bölümünü almak için bu işlevini çağırın.  
  
```  
CString GetItemName();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaynak görünen adı öğesi ad bölümünü [COleClientItem](../../mfc/reference/coleclientitem-class.md) oluşturucuda belirtilen.  
  
### <a name="remarks"></a>Açıklamalar  
 Dosya bilinen ad öğesi bilinen ad ile birlikte tam görünen adın sağlar.  
  
##  <a name="gettoprefix"></a>  COleChangeSourceDialog::GetToPrefix  
 Yeni önek dizesi kaynağı almak için bu işlevini çağırın.  
  
```  
CString GetToPrefix();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaynak yeni önek dizesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev yalnızca sonra çağrısı [DoModal](#domodal) döndürür **IDOK**.  
  
 Bu değer doğrudan geldiği **lpszTo** üyesi [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) yapısı.  
  
 Daha fazla bilgi için bkz: [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Windows SDK yapısı.  
  
##  <a name="m_cs"></a>  COleChangeSourceDialog::m_cs  
 Bu veri üyesi türünde bir yapıdır [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160).  
  
```  
OLEUICHANGESOURCE m_cs;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `OLEUICHANGESOURCE` OLE Kaynağı Değiştir iletişim kutusu davranışını denetlemek için kullanılır. Bu yapı üyeleri doğrudan değiştirilebilir.  
  
 Daha fazla bilgi için bkz: [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Windows SDK yapısı.  
  
##  <a name="isvalidsource"></a>  COleChangeSourceDialog::IsValidSource  
 Yeni kaynak geçerli olup olmadığını belirlemek için bu işlevini çağırın.  
  
```  
BOOL IsValidSource();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni kaynak geçerliyse, sıfır olmayan Aksi halde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev yalnızca sonra çağrısı [DoModal](#domodal) döndürür **IDOK**.  
  
 Daha fazla bilgi için bkz: [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Windows SDK yapısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COleDialog sınıfı](../../mfc/reference/coledialog-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
