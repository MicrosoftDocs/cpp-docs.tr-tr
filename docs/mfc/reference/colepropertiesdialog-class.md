---
title: "COlePropertiesDialog sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog::COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog::DoModal
- AFXODLGS/COlePropertiesDialog::OnApplyScale
- AFXODLGS/COlePropertiesDialog::m_gp
- AFXODLGS/COlePropertiesDialog::m_lp
- AFXODLGS/COlePropertiesDialog::m_op
- AFXODLGS/COlePropertiesDialog::m_psh
- AFXODLGS/COlePropertiesDialog::m_vp
dev_langs:
- C++
helpviewer_keywords:
- COlePropertiesDialog [MFC], COlePropertiesDialog
- COlePropertiesDialog [MFC], DoModal
- COlePropertiesDialog [MFC], OnApplyScale
- COlePropertiesDialog [MFC], m_gp
- COlePropertiesDialog [MFC], m_lp
- COlePropertiesDialog [MFC], m_op
- COlePropertiesDialog [MFC], m_psh
- COlePropertiesDialog [MFC], m_vp
ms.assetid: a54dbc89-1447-4329-bd01-00e98ec9e935
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a5460926e1f58a557b26d8e5fa0a0ed763fc5de6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="colepropertiesdialog-class"></a>COlePropertiesDialog sınıfı
Windows ortak OLE nesne özellikleri iletişim kutusu yalıtır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COlePropertiesDialog : public COleDialog  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COlePropertiesDialog::COlePropertiesDialog](#colepropertiesdialog)|Oluşturan bir `COlePropertiesDialog` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COlePropertiesDialog::DoModal](#domodal)|İletişim kutusu görüntüler ve bir seçim yapmasına olanak tanır.|  
|[COlePropertiesDialog::OnApplyScale](#onapplyscale)|Belge öğesi'nin ölçeklendirme değiştiğinde çerçevesi tarafından çağrılır.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COlePropertiesDialog::m_gp](#m_gp)|"Genel" sayfasını başlatmak için kullanılan bir yapı bir `COlePropertiesDialog` nesnesi.|  
|[COlePropertiesDialog::m_lp](#m_lp)|"Bağlantı" sayfasında başlatmak için kullanılan bir yapı bir `COlePropertiesDialog` nesnesi.|  
|[COlePropertiesDialog::m_op](#m_op)|Başlatmak için kullanılan bir yapı `COlePropertiesDialog` nesnesi.|  
|[COlePropertiesDialog::m_psh](#m_psh)|Ek özel özellik sayfaları eklemek için kullanılan yapısı.|  
|[COlePropertiesDialog::m_vp](#m_vp)|"Görünüm" sayfasında özelleştirmek için kullanılan bir yapı bir `COlePropertiesDialog` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ortak OLE nesne özellikleri iletişim kutusu görüntülemek ve OLE belge öğeyi Windows standartları ile tutarlı şekilde özelliklerini değiştirmek için kolay bir yol sağlar. Bu özellikler, diğerleriyle birlikte (öğesi bağlıysa) simgesine ve resim ölçekleme ve bilgi öğesi'nin bağlantıyı görüntülemek için seçenekler belge öğesi tarafından temsil edilen dosyası hakkında bilgi içerir.  
  
 Kullanılacak bir `COlePropertiesDialog` nesne, öncelikle nesnesini kullanarak oluşturmanız `COlePropertiesDialog` Oluşturucusu. İletişim kutusu oluşturulan sonra çağrı `DoModal` üye işlevi iletişim kutusunu görüntülemek ve hiçbir öğe özelliklerini değiştirmek kullanıcı izin vermek için. `DoModal`Kullanıcı Tamam seçili olup olmadığını döndürür ( **IDOK**) veya İptal'i ( **IDCANCEL**) düğmesi. Tamam ve İptal düğmeleri yanı sıra bir Uygula düğmesi yoktur. Kullanıcı Uygula seçtiğinde, belge öğesi özelliklerine yapılan değişiklikler öğesine uygulanır ve görüntüsünü otomatik olarak güncelleştirilir, ancak etkin kalır.  
  
 [M_psh](#m_psh) veri üyesi olan bir işaretçi bir **PROPSHEETHEADER** yapısını ve çoğu durumda değil gerekir açıkça erişim. Varsayılan Genel, Görünüm ve bağlantı sayfaları ötesinde ek özellik sayfaları gerektiğinde bir istisnadır. Bu durumda, değiştirebileceğiniz `m_psh` özel sayfalarınızın çağırmadan önce eklenecek veri üyesi `DoModal` üye işlevi.  
  
 OLE iletişim kutuları hakkında daha fazla bilgi için bkz: [ole'deki iletişim kutuları](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COlePropertiesDialog`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxodlgs.h  
  
##  <a name="colepropertiesdialog"></a>COlePropertiesDialog::COlePropertiesDialog  
 Oluşturur bir `COlePropertiesDialog` nesnesi.  
  
```  
COlePropertiesDialog(
    COleClientItem* pItem,  
    UINT nScaleMin = 10,  
    UINT nScaleMax = 500,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pItem`  
 Özellikleri erişilen belge öğesi işaretçisi.  
  
 *nScaleMin*  
 Belge öğesi görüntüsü yüzdesi ölçekleme en az.  
  
 *nScaleMax*  
 Ölçeklendirme yüzdesini belge öğesi görüntüsü için üst sınırı.  
  
 `pParentWnd`  
 İletişim kutusunun üst veya sahibi işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Ortak OLE nesne özellikleri iletişim kutusu sınıfından türetilen `COlePropertiesDialog` belge öğelerinizi ölçeklendirme uygulamak için. Bu sınıfın bir örneği tarafından uygulanan herhangi bir iletişim kutusu belge öğesi'nin ölçeklendirme desteklemez.  
  
 Varsayılan olarak, üç varsayılan sayfa ortak OLE nesne özellikleri iletişim kutusu vardır:  
  
-   Genel  
  
     Bu sayfa seçilen belge öğesi tarafından temsil edilen dosyasının sistem bilgilerini içerir. Bu sayfadan kullanıcı seçili öğe başka bir türüne dönüştürülemiyor.  
  
-   Görüntüle  
  
     Bu sayfa öğeyi görüntülemek, simgeyi değiştirme ve görüntüsü ölçeklendirmesinin değişmesi seçenekleri içerir.  
  
-   Bağlantı  
  
     Bu sayfa bağlantılı öğesi konumunu değiştirme ve bağlantılı öğesi güncelleştirme için seçenekleri içerir. Bu sayfadan kullanıcı seçilen öğenin bağlantısını kesebilirsiniz.  
  
 Varsayılan olarak sağlanan ötesinde sayfaları eklemek, değiştirmek [m_psh](#m_psh) oluşturucusunun çıkmadan önce üye değişkeni, `COlePropertiesDialog`-türetilmiş sınıf. Bu gelişmiş uygulamasıdır `COlePropertiesDialog` Oluşturucusu.  
  
##  <a name="domodal"></a>COlePropertiesDialog::DoModal  
 Windows ortak OLE nesne özellikleri iletişim kutusunu görüntüleyin ve görüntülemek ve/veya belge öğesi çeşitli özelliklerini değiştirmek kullanıcı izin vermek için bu üye işlevini çağırın.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **IDOK** veya **IDCANCEL** başarılı; Aksi halde 0 ise. **IDOK** ve **IDCANCEL** kullanıcı Tamam'ı veya iptal düğmesine seçili olmadığını gösterecek sabittir.  
  
 Varsa **IDCANCEL** döndürülür Windows çağırabilir [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) işlevi bir hata oluşup oluşmadığını belirleyin.  
  
##  <a name="m_gp"></a>COlePropertiesDialog::m_gp  
 Türü yapısını [OLEUIGNRLPROPS](http://msdn.microsoft.com/library/windows/desktop/ms687297), OLE nesne özellikleri iletişim kutusu, genel sayfayı başlatmak için kullanılan.  
  
```  
OLEUIGNRLPROPS m_gp;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sayfa bir katıştırma boyutunu ve türünü gösterir ve Dönüştür iletişim kutusu için kullanıcı erişimi sağlar. Bu sayfa ayrıca bağlantı hedef nesne bir bağlantı olup olmadığını gösterir.  
  
 Daha fazla bilgi için **OLEUIGNRLPROPS** yapısı, Windows SDK konusuna bakın.  
  
##  <a name="m_lp"></a>COlePropertiesDialog::m_lp  
 Türü yapısını [OLEUILINKPROPS](http://msdn.microsoft.com/library/windows/desktop/ms680735), OLE nesne özellikleri iletişim kutusunun bağlantı sayfası başlatmak için kullanılan.  
  
```  
OLEUILINKPROPS m_lp;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sayfa bağlantılı öğesi konumunu gösterir ve güncelleştirme ya da öğesine bağlantıyı kes olanak tanır.  
  
 Daha fazla bilgi için **OLEUILINKPROPS** yapısı, Windows SDK konusuna bakın.  
  
##  <a name="m_op"></a>COlePropertiesDialog::m_op  
 Türü yapısını [OLEUIOBJECTPROPS](http://msdn.microsoft.com/library/windows/desktop/ms687199), kullanılan ortak bir OLE nesne özellikleri iletişim kutusu başlatılamadı.  
  
```  
OLEUIOBJECTPROPS m_op;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yapı genel, bağlantı ve görünüm sayfalarını başlatmak için kullanılan üyeler içerir.  
  
 Daha fazla bilgi için bkz: **OLEUIOBJECTPROPS** ve [OLEUILINKPROPS](http://msdn.microsoft.com/library/windows/desktop/ms680735) Windows SDK'sı yapılarda.  
  
##  <a name="m_psh"></a>COlePropertiesDialog::m_psh  
 Türü yapısını [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546), iletişim nesnesinin özelliklerini üyeleri depolar.  
  
```  
PROPSHEETHEADER m_psh;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturma sonrasında bir `COlePropertiesDialog` nesne kullanabileceğiniz `m_psh` çağırmadan önce iletişim kutusu çeşitli yönlerini ayarlamak için `DoModal` üye işlevi.  
  
 Değiştirirseniz `m_psh` veri üyesi doğrudan herhangi varsayılan davranışı geçersiz kılar.  
  
 Daha fazla bilgi için **PROPSHEETHEADER** yapısı, Windows SDK konusuna bakın.  
  
##  <a name="m_vp"></a>COlePropertiesDialog::m_vp  
 Türü yapısını [OLEUIVIEWPROPS](http://msdn.microsoft.com/library/windows/desktop/ms693751), OLE nesne özellikleri iletişim kutusunun görünümü sayfası başlatmak için kullanılan.  
  
```  
OLEUIVIEWPROPS m_vp;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sayfa "içerik" ve "simge" görünümlerini nesne arasında geçiş yapma ve kapsayıcı içinde ölçeklendirme değiştirmek kullanıcı sağlar. Nesne simge olarak gösterildiğinde de Simge Değiştir iletişim kutusu için kullanıcı erişimi sağlar.  
  
 Daha fazla bilgi için **OLEUIVIEWPROPS** yapısı, Windows SDK konusuna bakın.  
  
##  <a name="onapplyscale"></a>COlePropertiesDialog::OnApplyScale  
 Ölçeklendirme değeri değiştirildi ve Tamam'ı veya Uygula seçilmiş çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnApplyScale(
    COleClientItem* pItem,  
    int nCurrentScale,  
    BOOL bRelativeToOrig);
```  
  
### <a name="parameters"></a>Parametreler  
 `pItem`  
 Özellikleri erişilen belge öğesi işaretçisi.  
  
 `nCurrentScale`  
 İletişim ölçek sayısal değer.  
  
 *bRelativeToOrig*  
 Ölçeklendirme belge öğenin özgün boyutu için geçerli olup olmadığını gösterir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşleniyorsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama hiçbir şey yapmaz. Ölçeklendirme denetimlerini etkinleştirmek için bu işlevi geçersiz kılmanız gerekir.  
  
> [!NOTE]
>  Ortak OLE nesne özellikleri iletişim kutusu görüntülenmeden önce framework ile bu işlevi çağıran bir **NULL** için `pItem` için 1 `nCurrentScale`. Bu, ölçekleme denetimleri etkin olmadığını belirlemek için gerçekleştirilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek DAİ](../../visual-cpp-samples.md)   
 [COleDialog sınıfı](../../mfc/reference/coledialog-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleDialog sınıfı](../../mfc/reference/coledialog-class.md)   
 [CPropertyPage Sınıfı](../../mfc/reference/cpropertypage-class.md)
