---
title: "CPageSetupDialog sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPageSetupDialog
- AFXDLGS/CPageSetupDialog
- AFXDLGS/CPageSetupDialog::CPageSetupDialog
- AFXDLGS/CPageSetupDialog::CreatePrinterDC
- AFXDLGS/CPageSetupDialog::DoModal
- AFXDLGS/CPageSetupDialog::GetDeviceName
- AFXDLGS/CPageSetupDialog::GetDevMode
- AFXDLGS/CPageSetupDialog::GetDriverName
- AFXDLGS/CPageSetupDialog::GetMargins
- AFXDLGS/CPageSetupDialog::GetPaperSize
- AFXDLGS/CPageSetupDialog::GetPortName
- AFXDLGS/CPageSetupDialog::OnDrawPage
- AFXDLGS/CPageSetupDialog::PreDrawPage
- AFXDLGS/CPageSetupDialog::m_psd
dev_langs:
- C++
helpviewer_keywords:
- CPageSetupDialog [MFC], CPageSetupDialog
- CPageSetupDialog [MFC], CreatePrinterDC
- CPageSetupDialog [MFC], DoModal
- CPageSetupDialog [MFC], GetDeviceName
- CPageSetupDialog [MFC], GetDevMode
- CPageSetupDialog [MFC], GetDriverName
- CPageSetupDialog [MFC], GetMargins
- CPageSetupDialog [MFC], GetPaperSize
- CPageSetupDialog [MFC], GetPortName
- CPageSetupDialog [MFC], OnDrawPage
- CPageSetupDialog [MFC], PreDrawPage
- CPageSetupDialog [MFC], m_psd
ms.assetid: 049c0ac8-f254-4854-9414-7a8271d1447a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3ca193c59c5d9c914f5bf8827601f389c546ea85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cpagesetupdialog-class"></a>CPageSetupDialog sınıfı
Ayar ve boşluklarının değiştirme için ek destek ile Windows ortak OLE Sayfa Yapısı iletişim kutusu tarafından sağlanan hizmetlerin yalıtır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CPageSetupDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog)|Oluşturan bir `CPageSetupDialog` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPageSetupDialog::CreatePrinterDC](#createprinterdc)|Yazdırma için cihaz bağlamı oluşturur.|  
|[CPageSetupDialog::DoModal](#domodal)|İletişim kutusu görüntüler ve kullanıcı yapma seçimi sağlar.|  
|[CPageSetupDialog::GetDeviceName](#getdevicename)|Yazıcı aygıt adını döndürür.|  
|[CPageSetupDialog::GetDevMode](#getdevmode)|Geçerli döndürür `DEVMODE` yazıcı.|  
|[CPageSetupDialog::GetDriverName](#getdrivername)|Yazıcı tarafından kullanılan sürücü döndürür.|  
|[CPageSetupDialog::GetMargins](#getmargins)|Yazıcı geçerli kenar boşluğu ayarlarını döndürür.|  
|[CPageSetupDialog::GetPaperSize](#getpapersize)|Yazıcı kağıt boyutu döndürür.|  
|[CPageSetupDialog::GetPortName](#getportname)|Çıkış bağlantı noktası adını döndürür.|  
|[CPageSetupDialog::OnDrawPage](#ondrawpage)|Yazdırılan sayfasının ekran görüntüsü oluşturmak için çerçevesi tarafından çağrılır.|  
|[CPageSetupDialog::PreDrawPage](#predrawpage)|Yazdırılan sayfasının ekran görüntüsü işlemeden önce çerçevesi tarafından çağrılır.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPageSetupDialog::m_psd](#m_psd)|Özelleştirmek için kullanılan bir yapı bir `CPageSetupDialog` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, Sayfa Yapısı iletişim kutusu gerçekleşmesi için tasarlanmıştır.  
  
 Kullanılacak bir `CPageSetupDialog` nesne, öncelikle nesnesini kullanarak oluşturmanız `CPageSetupDialog` Oluşturucusu. İletişim kutusu oluşturulan sonra ayarlamak veya herhangi bir değer değiştirmek `m_psd` , iletişim kutusunun denetimlerinin değerlerini başlatmak için veri üyesi. [M_psd](#m_psd) yapısıdır türü **PAGESETUPDLG**.  
  
 İletişim kutusu denetimleri başlatılıyor sonra çağrı `DoModal` üye işlevi iletişim kutusunu görüntülemek ve yazdırma seçeneklerini seçmek kullanıcı izin vermek için. `DoModal`Kullanıcı Tamam seçili olup olmadığını döndürür ( **IDOK**) veya iptal ( **IDCANCEL**) düğmesi.  
  
 Varsa `DoModal` döndürür **IDOK**, birkaç kullanabilirsiniz `CPageSetupDialog`'s üye işlevleri veya erişim `m_psd` kullanıcı tarafından bilgi girişlerini almak için veri üyesi.  
  
> [!NOTE]
>  Ortak bir OLE Sayfa Yapısı iletişim kutusu kapatıldıktan sonra çerçevesi tarafından kullanıcı tarafından yapılan değişiklikler kaydedilmeyecek. Bu iletişim kutusundan tüm değerleri uygulamanın belge veya uygulama sınıfı üyesi gibi kalıcı bir konuma kaydetmek için uygulamanın kendisinin kadar olur.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPageSetupDialog`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdlgs.h  
  
##  <a name="cpagesetupdialog"></a>CPageSetupDialog::CPageSetupDialog  
 Oluşturmak için bu işlevi çağırmak bir `CPageSetupDialog` nesnesi.  
  
```  
CPageSetupDialog(
    DWORD dwFlags = PSD_MARGINS | PSD_INWININIINTLMEASURE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwFlags`  
 İletişim kutusu ayarlarını özelleştirmek için kullanabileceğiniz bir veya daha fazla bayraklar. Değerlerin Bitsel veya işleci kullanılarak birleştirilebilir. Bu değerleri şu anlama gelir:  
  
- **PSD_DEFAULTMINMARGINS** yazıcının zamanlayıcısındaki aynı olacak şekilde sayfa kenar boşlukları için izin verilen en düşük genişlikleri ayarlar. Bu bayrak yoksayılır **PSD_MARGINS** ve **PSD_MINMARGINS** bayrakları da belirtilmiş.  
  
- **PSD_INWININIINTLMEASURE** uygulanmadı.  
  
- **PSD_MINMARGINS** belirtilen değerleri kullanmak sistem neden **rtMinMargin** üye sol, üst, sağ ve alt kenar boşlukları için izin verilen en düşük genişlikleri olarak. Sistem, kullanıcının belirtilen minimum'dan küçük bir genişliğe geçmesini engeller. Varsa **PSD_MINMARGINS** belirtilmezse, sistem yazıcı tarafından izin verdiği en az izin verilen genişliğini ayarlar.  
  
- **PSD_MARGINS** kenar boşluğu denetim alanı etkinleştirir.  
  
- **PSD_INTHOUSANDTHSOFINCHES** inç 1/1000 aralığında ölçülecek birimleri iletişim kutusunun neden olur.  
  
- **PSD_INHUNDREDTHSOFMILLIMETERS** 1/100 bir milimetrenin ölçülecek birimleri iletişim kutusunun neden olur.  
  
- **PSD_DISABLEMARGINS** kenar boşluğu iletişim kutusu denetimleri devre dışı bırakır.  
  
- **PSD_DISABLEPRINTER** yazıcı düğmesini devre dışı bırakır.  
  
- **PSD_NOWARNING** uyarı iletisi hiçbir varsayılan yazıcı olduğunda görüntülenmesini engeller.  
  
- **PSD_DISABLEORIENTATION** sayfa yönlendirmesini iletişim denetimini devre dışı bırakır.  
  
- **PSD_RETURNDEFAULT** neden `CPageSetupDialog` döndürülecek [aygıt MODUNDAN](http://msdn.microsoft.com/library/windows/desktop/dd183565) ve [DEVNAMES](../../mfc/reference/devnames-structure.md) sistem varsayılan yazıcı için bir iletişim kutusu görüntülenmeden başlatılır yapıları. Her iki varsayılır **hDevNames** ve **hDevMode** olan **NULL**; Aksi halde, işlev hata döndürür. Bir eski yazıcı sürücüsü tarafından ('den önceki Windows sürüm 3.0), sistem varsayılan yazıcı destekleniyorsa yalnızca **hDevNames** döndürülür; **hDevMode** olan **NULL**.  
  
- **PSD_DISABLEPAPER** kağıt seçim denetimi devre dışı bırakır.  
  
- **PSD_SHOWHELP** Yardım düğmesini göstermek iletişim kutusunun neden olur. **HwndOwner** üye olmamalıdır **NULL** Bu bayrak belirtilmezse.  
  
- **PSD_ENABLEPAGESETUPHOOK** belirtilen kanca işlevini etkinleştirir **lpfnSetupHook**.  
  
- **PSD_ENABLEPAGESETUPTEMPLATE** Oluştur iletişim kutusu tarafından tanımlanan iletişim şablonu kutusunu kullanarak işletim sisteminin neden **HINSTANCE** ve **lpSetupTemplateName**.  
  
- **PSD_ENABLEPAGESETUPTEMPLATEHANDLE** belirten **HINSTANCE** önceden iletişim kutusu şablonu içeren bir veri bloğunun tanımlar. Sistem yoksayar **lpSetupTemplateName** Bu bayrak belirtilmezse.  
  
- **PSD_ENABLEPAGEPAINTHOOK** belirtilen kanca işlevini etkinleştirir **lpfnPagePaintHook**.  
  
- **PSD_DISABLEPAGEPAINTING** iletişim kutusunun çizim alanı devre dışı bırakır.  
  
 `pParentWnd`  
 İletişim kutusunun üst veya sahibi işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [DoModal](../../mfc/reference/cdialog-class.md#domodal) işlevi iletişim kutusunu görüntüleyin.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#94](../../mfc/codesnippet/cpp/cpagesetupdialog-class_1.cpp)]  
  
##  <a name="createprinterdc"></a>CPageSetupDialog::CreatePrinterDC  
 Bir yazıcı cihaz bağlamı oluşturur [aygıt MODUNDAN](http://msdn.microsoft.com/library/windows/desktop/dd183565) ve [DEVNAMES](../../mfc/reference/devnames-structure.md) yapıları.  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan yazıcı cihaz bağlamı (DC) işler.  
  
##  <a name="domodal"></a>CPageSetupDialog::DoModal  
 Windows ortak OLE Sayfa Yapısı iletişim kutusu görüntüler ve yazdırma kenar boşlukları, boyutuna ve yönüne kağıt ve hedef yazıcı gibi çeşitli yazdırma Kur seçeneklerini seçmek kullanıcı izin vermek için bu işlevini çağırın.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **IDOK** veya **IDCANCEL**. Varsa **IDCANCEL** olan döndürülen Windows çağrısı [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) işlevi bir hata oluşup oluşmadığını belirleyin.  
  
 **IDOK** ve **IDCANCEL** kullanıcı Tamam'ı veya iptal düğmesine seçili olmadığını gösterecek sabittir.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrıca, kullanıcı yazıcı kurulum seçenekleri ağ konumu ve seçili yazıcıya özgü özellikleri gibi erişebilirsiniz.  
  
 Üyeleri ayarlayarak çeşitli Sayfa Yapısı iletişim kutusu seçenekleri başlatmak istiyorsanız `m_psd` yapısı, bunu çağırmadan önce yapmanız gereken `DoModal`, ve sonra iletişim nesnesi oluşturulur. Çağırdıktan sonra `DoModal`, diğer üye işlevlerini ayarları veya kullanıcı tarafından bilgi giriş iletişim kutusuna almak için çağırın.  
  
 Kullanıcı tarafından girilen geçerli ayarları yaymak istiyorsanız, çağırmaya [CWinApp::SelectPrinter](../../mfc/reference/cwinapp-class.md#selectprinter). Bu işlev bilgileri alır `CPageSetupDialog` nesnesini başlatır ve uygun özniteliklere sahip yeni bir yazıcı DC seçer.  
  
 [!code-cpp[NVC_MFCDocView#95](../../mfc/codesnippet/cpp/cpagesetupdialog-class_2.cpp)]  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog).  
  
##  <a name="getdevicename"></a>CPageSetupDialog::GetDeviceName  
 Sonra bu işlevi çağırmak `DoModal` şu anda seçili yazıcının adını almak için.  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından kullanılan aygıt adı **CPageSetupDialog** nesnesi.  
  
##  <a name="getdevmode"></a>CPageSetupDialog::GetDevMode  
 Bu işlev çağrısı çağrıldıktan sonra `DoModal` yazıcı cihaz bağlamı hakkında bilgi almak için `CPageSetupDialog` nesnesi.  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 [Aygıt MODUNDAN](http://msdn.microsoft.com/library/windows/desktop/dd183565) aygıt başlatma ve bir yazıcı sürücüsü ortamı hakkında bilgi içeren veri yapısı. Bu yapı Windows tarafından gerçekleştirilecek bellek kilidini açmanız gerekir [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) Windows SDK'ın açıklanan işlevi.  
  
##  <a name="getdrivername"></a>CPageSetupDialog::GetDriverName  
 Bu işlev çağrısı çağrıldıktan sonra [DoModal](../../mfc/reference/cprintdialog-class.md#domodal) sistem tarafından tanımlanan yazıcı aygıt sürücüsünün adını almak için.  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CString` sistem tarafından tanımlanan sürücü adı belirtme.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir işaretçi kullanmak `CString` tarafından döndürülen nesne `GetDriverName` değeri olarak `lpszDriverName` çağrıda [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
##  <a name="getmargins"></a>CPageSetupDialog::GetMargins  
 Çağrı sonra bu işlevi çağırmak `DoModal` yazıcı aygıt sürücüsü kenar boşlukları alınamadı.  
  
```  
void GetMargins(
    LPRECT lpRectMargins,  
    LPRECT lpRectMinMargins) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *lpRectMargins*  
 İşaretçi bir [RECT](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/18113766-3975-4369-bc07-92e34cba712e/locales/en-us) yapısı veya [CRect](../../atl-mfc-shared/reference/crect-class.md) (1/1000 inç veya 1/100 mm) şu anda seçili yazıcı yazdırma kenar boşluklarını tanımlayan nesne. Geçirmek **NULL** bu dikdörtgenin içindeki ilgilenen değilseniz, bu parametre için.  
  
 *lpRectMinMargins*  
 İşaretçi bir `RECT` yapısı veya `CRect` (1/1000 inç veya 1/100 mm) şu anda seçili yazıcı minimum yazdırma kenar boşluklarını tanımlayan nesne. Geçirmek **NULL** bu dikdörtgenin içindeki ilgilenen değilseniz, bu parametre için.  
  
##  <a name="getpapersize"></a>CPageSetupDialog::GetPaperSize  
 Yazdırma için seçtiğiniz kağıt boyutunu almak için bu işlevini çağırın.  
  
```  
CSize GetPaperSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) yazdırma için seçtiğiniz kağıt boyutuna (1/1000 inç veya 1/100 mm) içeren bir nesne.  
  
##  <a name="getportname"></a>CPageSetupDialog::GetPortName  
 Bu işlev çağrısı çağrıldıktan sonra `DoModal` şu anda seçili yazıcı bağlantı noktası adı alınamadı.  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şu anda seçili yazıcı bağlantı noktası adı.  
  
##  <a name="m_psd"></a>CPageSetupDialog::m_psd  
 Türü yapısını **PAGESETUPDLG**, iletişim nesnesinin özelliklerini üyeleri depolar.  
  
```  
PAGESETUPDLG m_psd;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturma sonrasında bir `CPageSetupDialog` nesne kullanabileceğiniz `m_psd` çağırmadan önce iletişim kutusu çeşitli yönlerini ayarlamak için `DoModal` üye işlevi.  
  
 Değiştirirseniz `m_psd` veri üyesi doğrudan herhangi varsayılan davranışı geçersiz kılar.  
  
 Daha fazla bilgi için [PAGESETUPDLG](http://msdn.microsoft.com/library/windows/desktop/ms646842) yapısı, Windows SDK konusuna bakın.  
  
 Örneğin bkz [CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog).  
  
##  <a name="ondrawpage"></a>CPageSetupDialog::OnDrawPage  
 Yazdırılan sayfasının ekran görüntüsü çizmek için çerçevesi tarafından çağrılır.  
  
```  
virtual UINT OnDrawPage(
    CDC* pDC,  
    UINT nMessage,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Yazıcı cihaz bağlamı işaretçi.  
  
 `nMessage`  
 Şu anda çizilen sayfa alanı belirten bir ileti belirtir. Aşağıdakilerden biri olabilir:  
  
- **WM_PSD_FULLPAGERECT** tüm sayfa alanı.  
  
- **WM_PSD_MINMARGINRECT** geçerli en düşük kenar boşlukları.  
  
- **WM_PSD_MARGINRECT** geçerli kenar boşlukları.  
  
- **WM_PSD_GREEKTEXTRECT** sayfasının içeriği.  
  
- **WM_PSD_ENVSTAMPRECT** posta damga temsili ayrılmış alanı.  
  
- **WM_PSD_YAFULLPAGERECT** alan için bir dönüş adresi gösterimi. Bu alan örnek sayfa alanın kenarlarına genişletir.  
  
 `lpRect`  
 İşaretçi bir [CRect](../../atl-mfc-shared/reference/crect-class.md) veya [RECT](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/18113766-3975-4369-bc07-92e34cba712e/locales/en-us) çizim alanının koordinatları içeren nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşleniyorsa sıfır olmayan bir değer; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu görüntü sonra ortak OLE Sayfa Yapısı iletişim kutusunun bir parçası görüntülenir. Varsayılan uygulama metin sayfasının bir resim çizer.  
  
 Resim veya görüntünün tamamını belirli bir alana çizim özelleştirmek için bu işlevi geçersiz kılar. Kullanarak bunu yapabilirsiniz bir `switch` deyimiyle **durum** değerini denetimi deyimleri `nMessage`. Örneğin, sayfa görüntüsü içeriğini çizmeye özelleştirmek için aşağıdaki kod örneği kullanabilirsiniz:  
  
 [!code-cpp[NVC_MFCDocView#96](../../mfc/codesnippet/cpp/cpagesetupdialog-class_3.cpp)]  
  
 Her durumunun işlemek gerekmez Not `nMessage`. Görüntü veya tüm alanının çeşitli bileşenleri görüntünün bir bileşen işlemek seçebilirsiniz.  
  
##  <a name="predrawpage"></a>CPageSetupDialog::PreDrawPage  
 Yazdırılan sayfasının ekran görüntüsü çizmeden önce çerçevesi tarafından çağrılır.  
  
```  
virtual UINT PreDrawPage(
    WORD wPaper,  
    WORD wFlags,  
    LPPAGESETUPDLG pPSD);
```  
  
### <a name="parameters"></a>Parametreler  
 *wPaper*  
 Kağıt boyutunu belirten bir değer belirtir. Bu değer şunlardan biri olabilir **DMPAPER_** değerleri listelenen açıklamasındaki [aygıt MODUNDAN](http://msdn.microsoft.com/library/windows/desktop/dd183565) yapısı.  
  
 `wFlags`  
 Kağıt veya Zarf yönünü belirtir ve yazıcı iğneli veya HPPCL (Hewlett Packard Yazıcı Denetim Dili) aygıtı olup. Bu parametre aşağıdaki değerlerden biri olabilir:  
  
-   Yatay modu (iğneli) 0x001 kağıt  
  
-   Yatay modu (HPPCL) 0x003 kağıt  
  
-   dikey moda (iğneli) 0x005 kağıt  
  
-   dikey moda (HPPCL) 0x007 kağıt  
  
-   0x00b Zarf yatay modunda (HPPCL)  
  
-   0x00d Zarf dikey modunda (iğneli)  
  
-   0x019 Zarf yatay modunda (iğneli)  
  
-   0x01f Zarf dikey modunda (iğneli)  
  
 `pPSD`  
 İşaretçi bir **PAGESETUPDLG** yapısı. Daha fazla bilgi için [PAGESETUPDLG](http://msdn.microsoft.com/library/windows/desktop/ms646842), Windows SDK konusuna bakın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşleniyorsa sıfır olmayan bir değer; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Resim çizim özelleştirmek için bu işlevi geçersiz kılar. Bu işlev geçersiz kılar ve dönüş **doğru**, görüntünün tamamını çizin. Bu işlev geçersiz kılar ve dönüş **yanlış**, tüm varsayılan görüntü çerçevesi tarafından çizilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek WORDPAD](../../visual-cpp-samples.md)   
 [CCommonDialog sınıfı](../../mfc/reference/ccommondialog-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



