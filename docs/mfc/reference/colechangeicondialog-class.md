---
title: "COleChangeIconDialog sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog::COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog::DoChangeIcon
- AFXODLGS/COleChangeIconDialog::DoModal
- AFXODLGS/COleChangeIconDialog::GetIconicMetafile
- AFXODLGS/COleChangeIconDialog::m_ci
dev_langs: C++
helpviewer_keywords:
- COleChangeIconDialog [MFC], COleChangeIconDialog
- COleChangeIconDialog [MFC], DoChangeIcon
- COleChangeIconDialog [MFC], DoModal
- COleChangeIconDialog [MFC], GetIconicMetafile
- COleChangeIconDialog [MFC], m_ci
ms.assetid: 8d6e131b-ddbb-4dff-a432-f239efda8e3d
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 237c1fcbea36c4e978ca19b14def4d57a4470973
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="colechangeicondialog-class"></a>COleChangeIconDialog sınıfı
OLE Simge Değiştir iletişim kutusu için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleChangeIconDialog : public COleDialog  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleChangeIconDialog::COleChangeIconDialog](#colechangeicondialog)|Oluşturan bir `COleChangeIconDialog` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleChangeIconDialog::DoChangeIcon](#dochangeicon)|İletişim kutusunda belirtilen değişiklik yapar.|  
|[COleChangeIconDialog::DoModal](#domodal)|OLE 2 Simge Değiştir iletişim kutusu görüntüler.|  
|[COleChangeIconDialog::GetIconicMetafile](#geticonicmetafile)|Bu öğe simge formla ilişkili meta dosyası için bir tanıtıcı alır.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleChangeIconDialog::m_ci](#m_ci)|İletişim kutusu davranışını denetleyen yapısı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıfın bir nesnesi oluşturma `COleChangeIconDialog` bu iletişim kutusunu çağırmak istediğinizde. Sonra bir `COleChangeIconDialog` nesne oluşturulan, kullanabileceğiniz [m_ci](#m_ci) yapısı değerleri veya iletişim kutusu denetimleri durumlarını başlatılamadı. `m_ci` Yapısıdır türü **OLEUICHANGEICON**. Bu iletişim kutusu sınıfı kullanma hakkında daha fazla bilgi için bkz: [DoModal](#domodal) üye işlevi.  
  
 Daha fazla bilgi için bkz: [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) Windows SDK'sındaki yapısı.  
  
 OLE özel iletişim kutuları hakkında daha fazla bilgi için bkz: [ole'deki iletişim kutuları](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeIconDialog`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxodlgs.h  
  
##  <a name="colechangeicondialog"></a>COleChangeIconDialog::COleChangeIconDialog  
 Bu işlev yalnızca oluşturan bir `COleChangeIconDialog` nesnesi.  
  
```  
explicit COleChangeIconDialog(
    COleClientItem* pItem,  
    DWORD dwFlags = CIF_SELECTCURRENT,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pItem`  
 Dönüştürülecek öğesine noktaları.  
  
 `dwFlags`  
 Aşağıdaki değerlerden herhangi bir sayıda içeren oluşturma bayrağı birleştirilmiş bitwise kullanarak- or işleci:  
  
- **CIF_SELECTCURRENT** iletişim kutusu çağrıldığında, geçerli radyo düğmesi'nin başlangıçta seçili olur belirtir. Bu varsayılandır.  
  
- **CIF_SELECTDEFAULT** iletişim kutusu çağrıldığında, varsayılan radyo düğmesi'nin başlangıçta seçili olur belirtir.  
  
- **CIF_SELECTFROMFILE** iletişim kutusu çağrıldığında, dosyadan radyo düğmesi'nin başlangıçta seçili olur belirtir.  
  
- **CIF_SHOWHELP** iletişim kutusu çağrıldığında Yardım düğmesi görüntülenir belirtir.  
  
- **CIF_USEICONEXE** simgesi belirtilen yürütülebilir dosya gelen ayıklanması gereken belirtir **szIconExe** alanını [m_ci](#m_ci) yerine türünden alınan. OLE olmayan dosyalar için bağlama veya katıştırmak için kullanışlıdır.  
  
 `pParentWnd`  
 İşaret üst veya sahibi pencere nesnesi için (tür `CWnd`) iletişim nesnesi ait olduğu. Eğer öyleyse **NULL**, iletişim kutusunun üst pencere ana uygulama penceresine ayarlanır.  
  
### <a name="remarks"></a>Açıklamalar  
 İletişim kutusunu görüntülemek için arama [DoModal](#domodal) işlevi.  
  
 Daha fazla bilgi için bkz: [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) Windows SDK'sındaki yapısı.  
  
##  <a name="dochangeicon"></a>COleChangeIconDialog::DoChangeIcon  
 İletişim kutusunda sonra seçilen bir öğeyi temsil eden simgeyi değiştirmek için bu işlevi çağırmak [DoModal](#domodal) döndürür **IDOK**.  
  
```  
BOOL DoChangeIcon(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>Parametreler  
 `pItem`  
 Simgesini değiştirme öğesi noktalarına.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Değiştirme başarılı olduğunda sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="domodal"></a>COleChangeIconDialog::DoModal  
 OLE Simge Değiştir iletişim kutusu görüntülemek için bu işlevini çağırın.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tamamlanma durumu iletişim kutusu için. Aşağıdaki değerlerden biri:  
  
- **IDOK** iletişim kutusu başarıyla görüntüleniyorsa.  
  
- **IDCANCEL** kullanıcı iletişim kutusunu iptal ederseniz.  
  
- **IDABORT** durumunda bir hata oluştu. Varsa **IDABORT** olan döndürülen arama `COleDialog::GetLastError` oluştu hata türü hakkında daha fazla bilgi almak için üye işlevi. Olası hatalar listesi için bkz: [OleUIChangeIcon](http://msdn.microsoft.com/library/windows/desktop/ms688307) Windows SDK'sındaki işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Üyeleri ayarlayarak çeşitli iletişim kutusu denetimleri başlatmak istiyorsanız [m_ci](#m_ci) yapısı, bu çağırmadan önce yapmanız gerektiğini `DoModal`, ancak iletişim nesnesi oluşturulur.  
  
 Varsa `DoModal` döndürür **IDOK**, diğer üye ayarları veya kullanıcı tarafından iletişim kutusuna giriş bilgileri almak için işlevleri çağırabilir.  
  
##  <a name="geticonicmetafile"></a>COleChangeIconDialog::GetIconicMetafile  
 Seçilen öğenin simge en boy içeren meta dosyası için bir tanıtıcı almak için bu işlevini çağırın.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İletişim kutusunu seçerek kapatıldığında yeni simgesine simge yönünü içeren meta dosyası için tanıtıcı **Tamam**; Aksi halde, simgesi olarak iletişim kutusunda görüntülenen önce oluştu.  
  
##  <a name="m_ci"></a>COleChangeIconDialog::m_ci  
 Türü yapısını **OLEUICHANGEICON** Simge Değiştir iletişim kutusu davranışını denetlemek için kullanılır.  
  
```  
OLEUICHANGEICON m_ci;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yapı üyeleri, doğrudan ya da üye işlevleri üzerinden değiştirilebilir.  
  
 Daha fazla bilgi için bkz: [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) Windows SDK'sındaki yapısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COleDialog sınıfı](../../mfc/reference/coledialog-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleDialog sınıfı](../../mfc/reference/coledialog-class.md)
