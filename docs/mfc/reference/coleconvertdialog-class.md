---
title: "COleConvertDialog sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleConvertDialog
- AFXODLGS/COleConvertDialog
- AFXODLGS/COleConvertDialog::COleConvertDialog
- AFXODLGS/COleConvertDialog::DoConvert
- AFXODLGS/COleConvertDialog::DoModal
- AFXODLGS/COleConvertDialog::GetClassID
- AFXODLGS/COleConvertDialog::GetDrawAspect
- AFXODLGS/COleConvertDialog::GetIconicMetafile
- AFXODLGS/COleConvertDialog::GetSelectionType
- AFXODLGS/COleConvertDialog::m_cv
dev_langs: C++
helpviewer_keywords:
- COleConvertDialog [MFC], COleConvertDialog
- COleConvertDialog [MFC], DoConvert
- COleConvertDialog [MFC], DoModal
- COleConvertDialog [MFC], GetClassID
- COleConvertDialog [MFC], GetDrawAspect
- COleConvertDialog [MFC], GetIconicMetafile
- COleConvertDialog [MFC], GetSelectionType
- COleConvertDialog [MFC], m_cv
ms.assetid: a7c57714-31e8-4b78-834d-8ddd1b856a1c
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 72de3b05dad581b2b0f4f3eec19e15d211bba601
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="coleconvertdialog-class"></a>COleConvertDialog sınıfı
Daha fazla bilgi için bkz: [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) Windows SDK'sındaki yapısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleConvertDialog : public COleDialog  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleConvertDialog::COleConvertDialog](#coleconvertdialog)|Oluşturan bir `COleConvertDialog` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleConvertDialog::DoConvert](#doconvert)|İletişim kutusunda belirtilen dönüşüm yapar.|  
|[COleConvertDialog::DoModal](#domodal)|OLE maddesini değiştir iletişim kutusu görüntüler.|  
|[COleConvertDialog::GetClassID](#getclassid)|Alır **CLSID** Seçilen öğeyle ilişkili.|  
|[COleConvertDialog::GetDrawAspect](#getdrawaspect)|Öğeyi bir simge olarak çizileceğini belirtir.|  
|[COleConvertDialog::GetIconicMetafile](#geticonicmetafile)|Bu öğe simge formla ilişkili meta dosyası için bir tanıtıcı alır.|  
|[COleConvertDialog::GetSelectionType](#getselectiontype)|Seçilen seçim türünü alır.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleConvertDialog::m_cv](#m_cv)|İletişim kutusu davranışını denetleyen yapısı.|  
  
## <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Uygulama Sihirbazı tarafından oluşturulan kapsayıcı kodu bu sınıfı kullanır.  
  
 OLE özel iletişim kutuları hakkında daha fazla bilgi için bkz: [ole'deki iletişim kutuları](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleConvertDialog`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxodlgs.h  
  
##  <a name="coleconvertdialog"></a>COleConvertDialog::COleConvertDialog  
 Yalnızca oluşturan bir `COleConvertDialog` nesnesi.  
  
```  
explicit COleConvertDialog (
    COleClientItem* pItem,
    DWORD dwFlags = CF_SELECTCONVERTTO,
    CLSID* pClassID = NULL,
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pItem`  
 Dönüştürülen veya etkinleştirilmesini öğesine noktaları.  
  
 `dwFlags`  
 Aşağıdaki değerlerden herhangi bir sayıda içeren oluşturma bayrağı birleştirilmiş bitwise kullanarak- or işleci:  
  
- **CF_SELECTCONVERTTO** iletişim kutusu çağrıldığında, dönüştürmek için radyo düğmesi'nin başlangıçta seçili olur belirtir. Bu varsayılandır.  
  
- **CF_SELECTACTIVATEAS** iletişim kutusu çağrıldığında, etkinleştirme olarak radyo düğmesi'nin başlangıçta seçili olur belirtir.  
  
- **CF_SETCONVERTDEFAULT** belirleyen sınıfı olan **CLSID** tarafından belirtilen **clsidConvertDefault** üyesi `m_cv` yapısı varsayılan olarak kullanılır Dönüştürülecek radyo düğmesi seçildiğinde sınıf listesi kutusunda seçim.  
  
- **CF_SETACTIVATEDEFAULT** belirleyen sınıfı olan **CLSID** tarafından belirtilen **clsidActivateDefault** üyesi `m_cv` yapısı varsayılan olarak kullanılır Etkinleştirme olarak radyo düğmesi seçildiğinde sınıf listesi kutusunda seçim.  
  
- **CF_SHOWHELPBUTTON** iletişim kutusu çağrıldığında Yardım düğmesi görüntülenir belirtir.  
  
 `pClassID`  
 Dönüştürülen veya etkinleştirilmesini öğenin CLSID'si noktalarına. Varsa **NULL**, **CLSID** ile ilişkili `pItem` kullanılır.  
  
 `pParentWnd`  
 İşaret üst veya sahibi pencere nesnesi için (tür `CWnd`) iletişim nesnesi ait olduğu. Eğer öyleyse **NULL**, iletişim kutusunun üst pencere ana uygulama penceresine ayarlanır.  
  
### <a name="remarks"></a>Açıklamalar  
 İletişim kutusunu görüntülemek için arama [DoModal](#domodal) işlevi.  
  
 Daha fazla bilgi için bkz: [CLSID anahtarı](http://msdn.microsoft.com/library/windows/desktop/ms691424) ve [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) yapısı.  
  
##  <a name="doconvert"></a>COleConvertDialog::DoConvert  
 Başarıyla döndürme sonra bu işlevi çağırmak [DoModal](#domodal)veya dönüştürmek için bir nesne türü etkinleştirmek için [COleClientItem](../../mfc/reference/coleclientitem-class.md).  
  
```  
BOOL DoConvert(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>Parametreler  
 `pItem`  
 Dönüştürülen veya etkinleştirilmesini öğesine noktaları. Olamaz **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Öğe dönüştürülen veya Dönüştür iletişim kutusu kullanıcı tarafından seçilen bilgileri göre etkin.  
  
##  <a name="domodal"></a>COleConvertDialog::DoModal  
 OLE Dönüştür iletişim kutusu görüntülemek için bu işlevini çağırın.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tamamlanma durumu iletişim kutusu için. Aşağıdaki değerlerden biri:  
  
- **IDOK** iletişim kutusu başarıyla görüntüleniyorsa.  
  
- **IDCANCEL** kullanıcı iletişim kutusunu iptal ederseniz.  
  
- **IDABORT** durumunda bir hata oluştu. Varsa **IDABORT** olan döndürülen arama [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) oluştu hata türü hakkında daha fazla bilgi almak için üye işlevi. Olası hatalar listesi için bkz: [OleUIConvert](http://msdn.microsoft.com/library/windows/desktop/ms680694) Windows SDK'sındaki işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Üyeleri ayarlayarak çeşitli iletişim kutusu denetimleri başlatmak istiyorsanız [m_cv](#m_cv) yapısı, bu çağırmadan önce yapmanız gerektiğini `DoModal`, ancak iletişim nesnesi oluşturulur.  
  
 Varsa `DoModal` döndürür **IDOK**, diğer üye ayarları veya kullanıcı tarafından iletişim kutusuna giriş bilgileri almak için işlevleri çağırabilir.  
  
##  <a name="getclassid"></a>COleConvertDialog::GetClassID  
 Almak için bu işlevi çağırmak **CLSID** Dönüştür iletişim kutusunda seçili kullanıcı öğeyle ilişkili.  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **CLSID** Dönüştür iletişim kutusunda seçili öğe ile ilişkilendirilmiş.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev yalnızca sonra çağrısı [DoModal](#domodal) döndürür **IDOK**.  
  
 Daha fazla bilgi için bkz: [CLSID anahtarı](http://msdn.microsoft.com/library/windows/desktop/ms691424) Windows SDK'sındaki.  
  
##  <a name="getdrawaspect"></a>COleConvertDialog::GetDrawAspect  
 Seçilen öğe bir simge olarak görüntülemek kullanıcının seçtiği olup olmadığını belirlemek için bu işlevini çağırın.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesneyi işlemek için gerekli yöntemi.  
  
- `DVASPECT_CONTENT`Simge olarak göster onay kutusu işaretli değilse döndürdü.  
  
- `DVASPECT_ICON`Simge olarak göster onay kutusu denetlendi döndürdü.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev yalnızca sonra çağrısı [DoModal](#domodal) döndürür **IDOK**.  
  
 En boy çizim daha fazla bilgi için bkz: [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki veri yapısı.  
  
##  <a name="geticonicmetafile"></a>COleConvertDialog::GetIconicMetafile  
 Seçilen öğenin simge en boy içeren meta dosyası için bir tanıtıcı almak için bu işlevini çağırın.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İletişim kutusu seçerek zaman kapatıldığında simge olarak göster onay kutusu ise, simge en boy seçilen öğenin içeren meta dosyası tanıtıcısını işaretli **Tamam**; Aksi halde **NULL**.  
  
##  <a name="getselectiontype"></a>COleConvertDialog::GetSelectionType  
 Dönüştür iletişim kutusunda seçili dönüştürme türünü belirlemek için bu işlevini çağırın.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yapılan seçim türü.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından belirtilen dönüş türü değerleri **seçimi** numaralandırma türü içinde bildirilen `COleConvertDialog` sınıfı.  
  
```  
enum Selection {
    noConversion,
    convertItem,
    activateAs
    };  
```  
  
 Bu değerlerin kısa açıklamaları izleyin:  
  
- **COleConvertDialog::noConversion** ya da iletişim kutusunda iptal edildi veya seçilen kullanıcı hiçbir dönüştürme döndürdü. Varsa `COleConvertDialog::DoModal` döndürülen **IDOK**, seçilen farklı bir simge olandan daha önce seçtiğiniz kullanıcı mümkündür.  
  
- **COleConvertDialog::convertItem** dönüştürmek için radyo düğmesi işaretlenirse, dönüştürmek için farklı bir öğeyi seçilen kullanıcı döndürülen ve `DoModal` döndürülen **IDOK**.  
  
- **COleConvertDialog::activateAs** kullanıcı etkinleştirme olarak radyo düğmesi işaretlediyseniz etkinleştirmek için farklı bir öğeyi seçilen döndürülen ve `DoModal` döndürülen **IDOK**.  
  
##  <a name="m_cv"></a>COleConvertDialog::m_cv  
 Türü yapısını **OLEUICONVERT** Dönüştür iletişim kutusu davranışını denetlemek için kullanılır.  
  
```  
OLEUICONVERT m_cv;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yapı üyeleri, doğrudan ya da üye işlevleri üzerinden değiştirilebilir.  
  
 Daha fazla bilgi için bkz: [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) Windows SDK'sındaki yapısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COleDialog sınıfı](../../mfc/reference/coledialog-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleDialog sınıfı](../../mfc/reference/coledialog-class.md)
