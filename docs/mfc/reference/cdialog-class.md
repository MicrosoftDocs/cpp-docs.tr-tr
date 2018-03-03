---
title: "CDialog sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDialog
- AFXWIN/CDialog
- AFXWIN/CDialog::CDialog
- AFXWIN/CDialog::Create
- AFXWIN/CDialog::CreateIndirect
- AFXWIN/CDialog::DoModal
- AFXWIN/CDialog::EndDialog
- AFXWIN/CDialog::GetDefID
- AFXWIN/CDialog::GotoDlgCtrl
- AFXWIN/CDialog::InitModalIndirect
- AFXWIN/CDialog::MapDialogRect
- AFXWIN/CDialog::NextDlgCtrl
- AFXWIN/CDialog::OnInitDialog
- AFXWIN/CDialog::OnSetFont
- AFXWIN/CDialog::PrevDlgCtrl
- AFXWIN/CDialog::SetDefID
- AFXWIN/CDialog::SetHelpID
- AFXWIN/CDialog::OnCancel
- AFXWIN/CDialog::OnOK
dev_langs:
- C++
helpviewer_keywords:
- CDialog [MFC], CDialog
- CDialog [MFC], Create
- CDialog [MFC], CreateIndirect
- CDialog [MFC], DoModal
- CDialog [MFC], EndDialog
- CDialog [MFC], GetDefID
- CDialog [MFC], GotoDlgCtrl
- CDialog [MFC], InitModalIndirect
- CDialog [MFC], MapDialogRect
- CDialog [MFC], NextDlgCtrl
- CDialog [MFC], OnInitDialog
- CDialog [MFC], OnSetFont
- CDialog [MFC], PrevDlgCtrl
- CDialog [MFC], SetDefID
- CDialog [MFC], SetHelpID
- CDialog [MFC], OnCancel
- CDialog [MFC], OnOK
ms.assetid: ca64b77e-2cd2-47e3-8eff-c2645ad578f9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 89c9670d19330e63a466c38a205a3122237e4f02
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cdialog-class"></a>CDialog sınıfı
İletişim kutuları ekranda görüntülemek için kullanılan temel sınıf.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDialog : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDialog::CDialog](#cdialog)|Oluşturan bir `CDialog` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDialog::Create](#create)|Başlatır `CDialog` nesnesi. Kalıcı olmayan iletişim kutusu oluşturur ve ona ekler `CDialog` nesnesi.|  
|[CDialog::CreateIndirect](#createindirect)|(Değil kaynak tabanlı) bellekteki bir iletişim kutusu şablondan kalıcı olmayan iletişim kutusu oluşturur.|  
|[CDialog::DoModal](#domodal)|Kalıcı iletişim kutusunu çağırır ve bittiğinde döndürür.|  
|[CDialog::EndDialog](#enddialog)|Kalıcı iletişim kutusunu kapatır.|  
|[CDialog::GetDefID](#getdefid)|Bir iletişim kutusu için varsayılan basma düğmesi denetiminin Kimliğini alır.|  
|[CDialog::GotoDlgCtrl](#gotodlgctrl)|İletişim kutusunda belirtilen iletişim kutusu denetimi odağı taşır.|  
|[CDialog::InitModalIndirect](#initmodalindirect)|(Değil kaynak tabanlı) bellekteki bir iletişim kutusu şablondan modal bir iletişim kutusu oluşturur. Parametreleri kadar işlevi depolanan `DoModal` olarak adlandırılır.|  
|[CDialog::MapDialogRect](#mapdialogrect)|İletişim kutusu birimleri dikdörtgenin ekran birimlerine dönüştürür.|  
|[CDialog::NextDlgCtrl](#nextdlgctrl)|İletişim kutusunda sonraki iletişim kutusu denetim odağı taşır.|  
|[CDialog::OnInitDialog](#oninitdialog)|İletişim kutusu başlatma büyütmek için geçersiz kılın.|  
|[CDialog::OnSetFont](#onsetfont)|Bir iletişim kutusu denetimi metin çizer yapılırken kullanılacak yazı tipini belirtmek için geçersiz kılın.|  
|[CDialog::PrevDlgCtrl](#prevdlgctrl)|İletişim kutusunda önceki iletişim kutusu denetimi odağı taşır.|  
|[CDialog::SetDefID](#setdefid)|Bir iletişim kutusu için varsayılan basma düğmesi denetimi için belirtilen bir basma düğmesi değiştirir.|  
|[CDialog::SetHelpID](#sethelpid)|İletişim kutusu için bir bağlama duyarlı Yardım kimlik ayarlar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDialog::OnCancel](#oncancel)|İptal düğmesi veya ESC anahtar eylemi gerçekleştirmek için geçersiz kılın. Varsayılan iletişim kutusunu kapatır ve **DoModal** döndürür **IDCANCEL**.|  
|[CDialog::OnOK](#onok)|Kalıcı iletişim kutusunda Tamam düğmesi eylemi gerçekleştirmek için geçersiz kılın. Varsayılan iletişim kutusunu kapatır ve `DoModal` döndürür **IDOK**.|  
  
## <a name="remarks"></a>Açıklamalar  
 İletişim kutusu iki tür vardır: kalıcı ve kalıcı olmayan. Uygulama devam etmeden önce bir modal iletişim kutusu kullanıcı tarafından kapatılması gerekir. Kalıcı olmayan iletişim kutusu iletişim kutusunu görüntülemek ve başka bir görev iptal etme veya iletişim kutusu kaldırma dönmek kullanıcı sağlar.  
  
 A `CDialog` nesne bir iletişim şablonunu birleşimidir ve `CDialog`-türetilmiş sınıf. İletişim şablonu oluşturmak ve bir kaynak olarak depolamak için iletişim kutusu düzenleyicisi kullanın ve sonra türetilmiş bir sınıf oluşturmak için sınıfı Ekle Sihirbazı'nı kullanın `CDialog`.  
  
 Diğer pencere gibi bir iletişim kutusu Windows iletilerini alır. Bir iletişim kutusunda, kullanıcı iletişim kutusu ile nasıl etkileşim kurduğu olduğundan iletişim kutusunun denetimlerden bildirim iletilerini işleme özellikle ilgilendiğiniz. İstediğiniz iletileri işleme ve ileti işleyicisi üye işlevleri ve uygun ileti eşleme girişleri sınıfa sizin için ekleyeceksiniz seçmek için Özellikler penceresini kullanın. Yalnızca işleyici üye işlevlerde uygulamaya özgü kod yazmanız gerekir.  
  
 Tercih ederseniz, her zaman ileti eşleme girişi ve üye işlevleri el ile yazabilirsiniz.  
  
 En basit iletişim kutusu dışındaki tüm ortamlarda, üye değişkenleri türetilmiş iletişim sınıfınızı iletişim kutusunun denetimlerinde kullanıcı tarafından girilen verileri depolamak için veya kullanıcı için verileri görüntülemek için ekleyin. Üye değişkenleri oluşturmak ve bunları denetimleri ile ilişkilendirmek için değişken Ekle Sihirbazı'nı kullanabilirsiniz. Aynı anda bir değişken türü ve izin verilen her değişken için değer aralığını seçin. Kod Sihirbazı'nı türetilmiş iletişim sınıfınızı üye değişkenleri ekler.  
  
 Üye değişkenleri ve iletişim kutusunun denetimleri arasındaki veri değişimini otomatik olarak işlemek için bir veri eşleme oluşturulur. Veri eşlemesini uygun değerlerle iletişim kutusunda denetimleri başlatmak, verileri almak ve veri doğrulama işlevleri sağlar.  
  
 Modal bir iletişim kutusu oluşturmak için bir nesne için türetilen iletişim sınıfınızı Oluşturucusu kullanılarak yığında oluşturun ve ardından çağırın `DoModal` iletişim kutusu penceresinin ve denetimlerini oluşturmak için. Kalıcı olmayan iletişim oluşturmak istiyorsanız, çağrı **oluşturma** iletişim sınıfınızı oluşturucuda.  
  
 Kullanarak bellekte bir şablon oluşturabilirsiniz bir [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) Windows SDK'ın açıklandığı gibi veri yapısı. Oluşturduktan sonra bir `CDialog` nesne, çağrı [CreateIndirect](#createindirect) bir geçici oluşturmak için iletişim kutusu veya çağrı [InitModalIndirect](#initmodalindirect) ve [DoModal](#domodal) kalıcı bir oluşturmak için iletişim kutusu.  
  
 Değişimi ve doğrulaması veri eşlemesi içinde geçersiz kılma yazılır `CWnd::DoDataExchange` yeni iletişim sınıfınızı eklenir. Bkz: [DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange) üye işlevinde `CWnd` değişimi ve doğrulaması işlevselliği hakkında daha fazla bilgi için.  
  
 Programcı ve framework çağrı `DoDataExchange` yapılan bir çağrı üzerinden dolaylı olarak [CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata).  
  
 Framework çağrıları `UpdateData` kullanıcı bir modal iletişim kutusunu kapatmak için Tamam düğmesine tıkladığında. (İptal düğmesine tıkladıysanız verileri alınamadı.) Varsayılan uygulaması [OnInitDialog](#oninitdialog) de çağırır `UpdateData` denetimlerin ilk değerleri ayarlamak için. Genellikle geçersiz kılma `OnInitDialog` daha fazla denetim başlatılamadı. `OnInitDialog`Tüm iletişim denetimleri oluşturulur ve hemen önce iletişim kutusu görüntülenir. sonra çağrılır.  
  
 Çağırabilirsiniz `CWnd::UpdateData` kalıcı veya geçici bir iletişim kutusu yürütülmesi sırasında herhangi bir zamanda.  
  
 Bir iletişim kutusu el ile ortaya çıkarsa, gerekli üye değişkenleri türetilmiş iletişim kutusu sınıfı kendiniz eklemeniz ve ayarlamak veya bu değerleri almak için üye işlevleri ekleyin.  
  
 Kullanıcı Tamam'ı veya İptal düğmeleri bastığında veya kodunuzu çağırdığında bir modal iletişim kutusu otomatik olarak kapanır `EndDialog` üye işlevi.  
  
 Kalıcı olmayan iletişim kutusu uyguladığınızda, her zaman geçersiz `OnCancel` üye fonksiyonu ve çağrı `DestroyWindow` gelen içindeki. Çağrı temel sınıfı yok `CDialog::OnCancel`çağırır çünkü `EndDialog`, iletişim kutusu görünmez yapar ancak onu yok etmez. Ayrıca kılmalıdır `PostNcDestroy` silmek için kalıcı olmayan iletişim kutuları için **bu**, kalıcı olmayan iletişim kutuları genellikle ile ayrılan beri **yeni**. Kalıcı iletişim kutuları çerçevesi genellikle oluşturulur ve gerekmeyen `PostNcDestroy` temizleme.  
  
 Daha fazla bilgi için `CDialog`, bkz:  
  
- [İletişim Kutuları](../../mfc/dialog-boxes.md)  
  
-   Bilgi Bankası makalesi Q262954: nasıl yapılır: bir Resizeable iletişim kutusu ile kaydırma çubukları oluşturma  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDialog`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="cdialog"></a>CDialog::CDialog  
 Kaynak tabanlı kalıcı bir iletişim kutusu oluşturmak için Oluşturucusu ortak biçimindeki çağırın.  
  
```  
explicit CDialog(
    LPCTSTR lpszTemplateName,  
    CWnd* pParentWnd = NULL);

 
explicit CDialog(
    UINT nIDTemplate,  
    CWnd* pParentWnd = NULL);  
  
CDialog();
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszTemplateName`  
 Bir iletişim kutusu şablon kaynağı adı null ile sonlandırılmış bir dize içeriyor.  
  
 `nIDTemplate`  
 Bir iletişim kutusu şablon kaynağı kimliği numarasını içerir.  
  
 `pParentWnd`  
 İşaret üst veya sahibi pencere nesnesi için (tür [CWnd](../../mfc/reference/cwnd-class.md)) iletişim nesnesi ait olduğu. Eğer öyleyse **NULL**, iletişim nesnenin üst pencere ana uygulama penceresine ayarlanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir form oluşturucusunun şablon adına göre iletişim kutusu kaynağı erişim sağlar. Diğer oluşturucuyu erişim şablon kimliği numarasıyla genellikle ile sağlayan bir **IDD_** önek (örneğin, IDD_DIALOG1).  
  
 Bellekte bir şablondan bir modal iletişim kutusu oluşturmak için önce parametresiz, korumalı Oluşturucusu çağırma ve ardından çağırın `InitModalIndirect`.  
  
 Modal bir iletişim kutusu yukarıdaki yöntemlerden biri ile oluşturduktan sonra arama `DoModal`.  
  
 Kalıcı olmayan iletişim kutusu oluşturmak için korumalı bir form kullanmak `CDialog` Oluşturucusu. Kalıcı olmayan iletişim kutusu uygulamak için kendi iletişim kutusu sınıfı türetilmesi gerekir çünkü Oluşturucusu korunur. Kalıcı olmayan iletişim kutusu yapımı iki adımlı bir işlemdir. İlk çağrıda Oluşturucusu; ' ı çağırın **oluşturma** kaynak tabanlı iletişim kutusu oluşturmak için üye işlevi veya arama `CreateIndirect` bellekte bir şablondan Oluştur iletişim kutusu için.  
  
##  <a name="create"></a>CDialog::Create  
 Çağrı **oluşturma** bir kaynaktan bir iletişim kutusu şablonu kullanarak bir kalıcı olmayan iletişim kutusu oluşturmak için.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszTemplateName,  
    CWnd* pParentWnd = NULL);

 
virtual BOOL Create(
    UINT nIDTemplate,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszTemplateName`  
 Bir iletişim kutusu şablon kaynağı adı null ile sonlandırılmış bir dize içeriyor.  
  
 `pParentWnd`  
 İşaret üst pencere nesnesi için (tür [CWnd](../../mfc/reference/cwnd-class.md)) iletişim nesnesi ait olduğu. Eğer öyleyse **NULL**, iletişim nesnenin üst pencere ana uygulama penceresine ayarlanır.  
  
 `nIDTemplate`  
 Bir iletişim kutusu şablon kaynağı kimliği numarasını içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her iki forms iletişim kutusu oluşturma ve başlatma başarılıysa sıfır olmayan döndürür; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı koyabilirsiniz **oluşturma** Oluşturucusu veya çağrısı içinde Oluşturucusu sonra çağrılır.  
  
 İki tür **oluşturma** üye işlevine sağlanan erişim iletişim kutusu şablon kaynağı için şablon adına veya şablon kimliği numarasını (örneğin, IDD_DIALOG1) tarafından.  
  
 Ya da form için üst pencere nesnesi için bir işaretçi geçirin. Varsa `pParentWnd` olan **NULL**, iletişim kutusu ana uygulama penceresini kendi üst veya sahibi penceresi ile oluşturulur.  
  
 **Oluşturma** hemen iletişim kutusu oluşturduktan sonra üye işlevi döndürür.  
  
 Kullanım **ws_vısıble** üst pencere oluşturulduğunda, iletişim kutusu görüntülendiğinde bu iletişim kutusu şablonunda stili. Aksi takdirde çağırmalısınız `ShowWindow`. Daha fazla iletişim kutusu stilleri ve kendi uygulama için bkz: [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) Windows SDK yapısı ve [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) içinde *MFC başvurusu*.  
  
 Kullanım `CWnd::DestroyWindow` tarafından oluşturulan bir iletişim kutusunu yok etme işlevi **oluşturma** işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCControlLadenDialog#62](../../mfc/codesnippet/cpp/cdialog-class_1.cpp)]  
  
##  <a name="createindirect"></a>CDialog::CreateIndirect  
 Bellekteki bir iletişim kutusu şablondan kalıcı olmayan iletişim kutusu oluşturmak için bu üye işlevini çağırın.  
  
```  
virtual BOOL CreateIndirect(
    LPCDLGTEMPLATE lpDialogTemplate,  
    CWnd* pParentWnd = NULL,  
    void* lpDialogInit = NULL);

 
virtual BOOL CreateIndirect(
    HGLOBAL hDialogTemplate,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpDialogTemplate`  
 İletişim kutusu oluşturmak için kullanılan bir iletişim kutusu şablon içeren bellek noktalarına. Bu şablon biçiminde olan bir [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) yapısı ve denetim bilgileri, Windows SDK'ın açıklandığı gibi.  
  
 `pParentWnd`  
 İşaret iletişim nesnenin üst pencere nesnesi için (tür [CWnd](../../mfc/reference/cwnd-class.md)). Eğer öyleyse **NULL**, iletişim nesnenin üst pencere ana uygulama penceresine ayarlanır.  
  
 `lpDialogInit`  
 İşaret eden bir **DLGINIT** kaynak.  
  
 `hDialogTemplate`  
 Bir iletişim kutusu şablonu içeren genel bellek için bir tanıtıcı içerir. Bu şablon biçiminde olan bir **DLGTEMPLATE** yapısı ve iletişim kutusunda her denetim için verileri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İletişim kutusu oluşturduysanız ve başarılı bir şekilde başlatıldı sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 `CreateIndirect` Hemen iletişim kutusu oluşturduktan sonra üye işlevi döndürür.  
  
 Kullanım **ws_vısıble** üst pencere oluşturulduğunda, iletişim kutusu görüntülendiğinde bu iletişim kutusu şablonunda stili. Aksi takdirde çağırmalısınız `ShowWindow` görüntülenmesine neden olacak. Nasıl şablonda diğer iletişim kutusu stilleri belirtebilirsiniz. daha fazla bilgi için bkz: [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) Windows SDK'sındaki yapısı.  
  
 Kullanım `CWnd::DestroyWindow` tarafından oluşturulan bir iletişim kutusunu yok etme işlevi `CreateIndirect` işlevi.  
  
 ActiveX denetimleri içeren iletişim kutuları sağlanan ek bilgileri gerektiren bir **DLGINIT** kaynak. Bilgi Bankası makalesi Q231591, daha fazla bilgi için bkz: "nasıl yapılır: bir MFC iletişim kutusu ile bir ActiveX denetimi oluşturmak için bir iletişim şablonunu kullanın." Bilgi Bankası makaleleri kullanılabilir [http://support.microsoft.com](http://support.microsoft.com/).  
  
##  <a name="domodal"></a>CDialog::DoModal  
 Kalıcı iletişim kutusunu çağırmak ve tamamlandığında iletişim kutusu sonucu dönmek için bu üye işlevini çağırın.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `int` değerini belirtir. değer `nResult` geçirilmedi parametresi [CDialog::EndDialog](#enddialog) iletişim kutusunu kapatmak için kullanılan üye işlevi. Dönüş değeri işlevi iletişim kutusu oluşturulamadı -1 ise veya **IDABORT** başka bir hata oluştuysa, bu durumda çıktı penceresi içerecek hata bilgileri [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Açıklamalar  
 İletişim kutusu etkinken bu üye işlevi tüm kullanıcıyla etkileşime işler. İletişim kutusu kalıcı kılan budur; diğer bir deyişle, kullanıcı iletişim kutusu kapatılana kadar diğer windows ile etkileşime giremezler.  
  
 Kullanıcı iletişim kutusunda Tamam'ı veya İptal'i, bir ileti işleyicisi üye fonksiyonu gibi pushbuttons birini gibi tıklarsa [OnOK](#onok) veya [OnCancel](#oncancel), iletişim kutusunu kapatmak denemek için çağrılır. Varsayılan `OnOK` üye işlevi doğrulamak ve iletişim kutusu veri güncelleştirilecek ve sonuç ile iletişim kutusunu kapatmak **IDOK**ve varsayılan `OnCancel` üye işlevi sonuç iletişim kutusuyla kapatılacak  **IDCANCEL** doğrulama veya iletişim kutusu verileri güncelleştirme olmadan. Bunların davranışı değiştirmek için bu ileti işleyici işlevleri geçersiz kılabilirsiniz.  
  
> [!NOTE]
> `PreTranslateMessage`kalıcı iletişim kutusu ileti işleme için şimdi denir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCControlLadenDialog#63](../../mfc/codesnippet/cpp/cdialog-class_2.cpp)]  
  
##  <a name="enddialog"></a>CDialog::EndDialog  
 Modal bir iletişim kutusu sonlandırmak için bu üye işlevini çağırın.  
  
```  
void EndDialog(int nResult);
```  
  
### <a name="parameters"></a>Parametreler  
 `nResult`  
 İletişim kutusundan çağırana döndürülecek değeri içeren `DoModal`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevinin döndürdüğü `nResult` dönüş değeri olarak `DoModal`. Kullanmalısınız `EndDialog` modal bir iletişim kutusu oluşturulduğunda işleme tamamlamak için işlevi.  
  
 Çağırabilirsiniz `EndDialog` herhangi bir zamanda bile [OnInitDialog](#oninitdialog), kapatın; bu durumda, önce iletişim kutusu gösterilir veya giriş odağını ayarlanmadan önce.  
  
 `EndDialog`iletişim kutusu hemen kapatmaz. Bunun yerine, geçerli ileti işleyicisini döndürür hemen kapatmak için iletişim kutusu yönlendiren bir bayrak ayarlar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCControlLadenDialog#64](../../mfc/codesnippet/cpp/cdialog-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCControlLadenDialog#65](../../mfc/codesnippet/cpp/cdialog-class_4.cpp)]  
  
##  <a name="getdefid"></a>CDialog::GetDefID  
 Çağrı `GetDefID` bir iletişim kutusu için varsayılan basma düğmesi denetiminin Kimliğini almak için üye işlevi.  
  
```  
DWORD GetDefID() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 32-bitlik bir değer ( `DWORD`). Varsayılan basma düğmesi bir kimlik değeri varsa, yüksek sıralı sözcüğünü içeren **DC_HASDEFID** ve düşük düzey sözcük kimliği değeri içeriyor. Varsayılan basma düğmesi kimliğe sahip değilse, dönüş değeri 0'dır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu genellikle bir Tamam düğmesine olur.  
  
##  <a name="gotodlgctrl"></a>CDialog::GotoDlgCtrl  
 İletişim kutusunda belirtilen denetim odağı taşır.  
  
```  
void GotoDlgCtrl(CWnd* pWndCtrl);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWndCtrl`  
 Odağı alacak penceresi (Denetim) tanımlar.  
  
### <a name="remarks"></a>Açıklamalar  
 (Olarak geçirmek için alt pencere) denetlemek için bir işaretçi almak için `pWndCtrl`, çağrı `CWnd::GetDlgItem` gösteren bir işaretçi döndürür üye işlevi bir [CWnd](../../mfc/reference/cwnd-class.md) nesnesi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CWnd::GetDlgItem](../../mfc/reference/cwnd-class.md#getdlgitem).  
  
##  <a name="initmodalindirect"></a>CDialog::InitModalIndirect  
 Bellekte oluşturmak bir iletişim kutusu şablonu kullanarak bir modal iletişim nesneyi başlatmak için bu üye işlevini çağırın.  
  
```  
BOOL InitModalIndirect(
    LPCDLGTEMPLATE lpDialogTemplate,  
    CWnd* pParentWnd = NULL,  
    void* lpDialogInit = NULL);

 
    BOOL InitModalIndirect(
    HGLOBAL hDialogTemplate,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpDialogTemplate`  
 İletişim kutusu oluşturmak için kullanılan bir iletişim kutusu şablon içeren bellek noktalarına. Bu şablon biçiminde olan bir [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) yapısı ve denetim bilgileri, Windows SDK'ın açıklandığı gibi.  
  
 `hDialogTemplate`  
 Bir iletişim kutusu şablonu içeren genel bellek için bir tanıtıcı içerir. Bu şablon biçiminde olan bir **DLGTEMPLATE** yapısı ve iletişim kutusunda her denetim için verileri.  
  
 `pParentWnd`  
 İşaret üst veya sahibi pencere nesnesi için (tür [CWnd](../../mfc/reference/cwnd-class.md)) iletişim nesnesi ait olduğu. Eğer öyleyse **NULL**, iletişim nesnenin üst pencere ana uygulama penceresine ayarlanır.  
  
 `lpDialogInit`  
 İşaret eden bir **DLGINIT** kaynak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İletişim nesnesi oluşturduysanız ve başarılı bir şekilde başlatıldı sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Modal bir iletişim kutusu dolaylı olarak oluşturmak için önce genel bir bellek bloğu ayırın ve iletişim kutusunu şablonla doldurun. Boş çağırın `CDialog` Oluşturucu iletişim kutusu nesnesi oluşturun. Ardından, çağrı `InitModalIndirect` bellek içi iletişim kutusu şablonu, tanıtıcıyı depolamak için. Windows iletişim kutusu oluşturulur ve görüntülenir daha sonra zaman [DoModal](#domodal) üye işlevi çağrılır.  
  
 ActiveX denetimleri içeren iletişim kutuları sağlanan ek bilgileri gerektiren bir **DLGINIT** kaynak. Bilgi Bankası makalesi Q231591, daha fazla bilgi için bkz: "nasıl yapılır: bir MFC iletişim kutusu ile bir ActiveX denetimi oluşturmak için bir iletişim şablonunu kullanın." Bilgi Bankası makaleleri kullanılabilir [http://support.microsoft.com](http://support.microsoft.com/).  
  
##  <a name="mapdialogrect"></a>CDialog::MapDialogRect  
 İletişim kutusu birimleri dikdörtgenin ekran birimlerine dönüştürmek üzere çağrılır.  
  
```  
void MapDialogRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `lpRect`  
 İşaret eden bir [RECT](../../mfc/reference/rect-structure1.md) yapısı veya [CRect](../../atl-mfc-shared/reference/crect-class.md) iletişim kutusu içeren nesne koordinatları dönüştürülecek.  
  
### <a name="remarks"></a>Açıklamalar  
 İletişim kutusu birimleri ortalama genişlik ve yükseklik yazı tipi iletişim kutusu metni için kullanılan karakter türetilmiş geçerli iletişim kutusu temel birim bakımından belirtilmiştir. Bir yatay bir dördüncü iletişim kutusu base-width biriminin birimidir ve bir dikey bir sekizinci iletişim kutusu temel yükseklik biriminin birimdir.  
  
 **GetDialogBaseUnits** Windows işlevi sistem yazı tipi boyutu bilgilerini döndürür, ancak kullanırsanız her iletişim kutusu için farklı bir yazı tipi belirtebilirsiniz **DS_SETFONT** içinde stili Kaynak tanımı dosyası. `MapDialogRect` Windows işlevi bu iletişim kutusu için uygun yazı tipini kullanır.  
  
 `MapDialogRect` Üye işlevi değiştirir iletişim kutusu birimleri `lpRect` ile dikdörtgen Oluştur iletişim kutusu veya bir kutu içinde bir denetim konumlandırmak için kullanılan böylece ekran birimler (piksel cinsinden).  
  
##  <a name="nextdlgctrl"></a>CDialog::NextDlgCtrl  
 İletişim kutusunda sonraki denetim odağı taşır.  
  
```  
void NextDlgCtrl() const;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Odak en son denetim iletişim kutusunda ise, ilk denetime taşır.  
  
##  <a name="oncancel"></a>CDialog::OnCancel  
 Kullanıcı tıklattığında framework bu yöntemi çağırır **iptal** veya kalıcı veya geçici iletişim kutusunda ESC tuşuna basar.  
  
```  
virtual void OnCancel();
```  
  
### <a name="remarks"></a>Açıklamalar  
 (Eski verileri geri yükleme gibi) eylemleri gerçekleştirmek için bu yöntemi geçersiz kılın kullanıcı kapattığı zaman iletişim kutusunu tıklatarak **iptal** veya ESC tuşuna basmak. Varsayılan çağırarak modal bir iletişim kutusu kapanır [EndDialog](#enddialog) ve neden [DoModal](#domodal) IDCANCEL dönün.  
  
 Öğesini uygularsanız **iptal** düğmesi kalıcı olmayan iletişim kutusunda, kılmalı `OnCancel` yöntemi ve çağrı [DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) içindeki. Bunu çağırdığı için temel sınıf yöntemi çağırmayın `EndDialog`, hangi iletişim kutusu görünmez yapma ancak destroy değil.  
  
> [!NOTE]
>  Kullandığınızda bu yöntemi geçersiz kılınamaz bir `CFileDialog` Windows XP altında derlenmiş bir programda nesnesi. Hakkında daha fazla bilgi için `CFileDialog`, bkz: [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCControlLadenDialog#66](../../mfc/codesnippet/cpp/cdialog-class_5.cpp)]  
  
##  <a name="oninitdialog"></a>CDialog::OnInitDialog  
 Bu yöntem, yanıt olarak çağrılır `WM_INITDIALOG` ileti.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Uygulama giriş odağını denetimleri birine iletişim kutusunda ayarlanmış olup olmadığını belirtir. Varsa `OnInitDialog` döndürür sıfır olmayan Windows ayarlar giriş odağını ilk denetim iletişim kutusunda varsayılan konumuna. Uygulama, yalnızca açıkça giriş odağını denetimleri birine iletişim kutusuna ayarlarsanız 0 geri dönebilirsiniz.  
  
### <a name="remarks"></a>Açıklamalar  
 Windows gönderir `WM_INITDIALOG` sırasında iletişim kutusuna ileti [oluşturma](#create), [CreateIndirect](#createindirect), veya [DoModal](#domodal) hemen önce iletişim kutusu ortaya çağrıları görüntülenir.  
  
 İletişim kutusu başlatıldığında özel işlem gerçekleştirmek istiyorsanız bu yöntemi geçersiz kılın. Geçersiz kılınan sürümünde ilk çağrı temel sınıfı `OnInitDialog` ancak dönüş değerini yoksayar. Genellikle döndürülecek `TRUE` geçersiz kılınan yönteminden.  
  
 Windows çağrıları `OnInitDialog` tüm Microsoft Foundation Class Kitaplığı iletişim kutuları için ortak standart genel iletişim kutusu yordamı kullanarak işlevi. Bu işlev, ileti eşlemesi aracılığıyla çağırmaz ve bu nedenle, bir ileti eşleme girişi için bu yöntem gerekmez.  
  
> [!NOTE]
>  Kullandığınızda bu yöntemi geçersiz kılınamaz bir `CFileDialog` nesneyi altında derlenmiş bir programda [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. Değişiklikler hakkında daha fazla bilgi için `CFileDialog` altında [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] bkz [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCControlLadenDialog#67](../../mfc/codesnippet/cpp/cdialog-class_6.cpp)]  
  
##  <a name="onok"></a>CDialog::OnOK  
 Kullanıcı tıklattığında adlı **Tamam** düğmesini (düğmesi, bir kimliği IDOK ile).  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eylemleri gerçekleştirmek için bu yöntemi geçersiz kılın zaman **Tamam** düğmesi etkinleştirilir. İletişim kutusu otomatik veri doğrulama hem de exchange içeriyorsa, bu yöntem varsayılan uygulaması iletişim kutusu verileri doğrular ve uygulamanızda uygun değişkenleri güncelleştirir.  
  
 Öğesini uygularsanız **Tamam** düğmesi kalıcı olmayan iletişim kutusunda, kılmalı `OnOK` yöntemi ve çağrı [DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) içindeki. Bunu çağırdığı için temel sınıf yöntemi çağırmayın [EndDialog](#enddialog) iletişim kutusu görünmez yapar ancak yok etmez.  
  
> [!NOTE]
>  Kullandığınızda bu yöntemi geçersiz kılınamaz bir `CFileDialog` Windows XP altında derlenmiş bir programda nesnesi. Hakkında daha fazla bilgi için `CFileDialog`, bkz: [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCControlLadenDialog#68](../../mfc/codesnippet/cpp/cdialog-class_7.cpp)]  
  
##  <a name="onsetfont"></a>CDialog::OnSetFont  
 Bir iletişim kutusu denetimi metin çizme için kullanacağı yazı tipini belirtir.  
  
```  
Virtual void OnSetFont(CFont* pFont);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pFont`  
 Bir işaretçi varsayılan yazı tipi bu iletişim kutusundaki tüm denetimler için kullanılan yazı tipini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 İletişim kutusu, tüm denetimler için varsayılan olarak belirtilen yazı tipi kullanın.  
  
 İletişim kutusu Düzenleyicisi iletişim kutusu yazı tipi iletişim kutusu şablon kaynağı bir parçası olarak tipik olarak ayarlar.  
  
> [!NOTE]
>  Kullandığınızda bu yöntemi geçersiz kılınamaz bir `CFileDialog` nesneyi altında derlenmiş bir programda [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. Değişiklikler hakkında daha fazla bilgi için `CFileDialog` altında [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] bkz [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md).  
  
##  <a name="prevdlgctrl"></a>CDialog::PrevDlgCtrl  
 Odağı önceki denetim iletişim kutusunda ayarlar.  
  
```  
void PrevDlgCtrl() const;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 İletişim kutusunda ilk denetim odağı altındadır, kutusundaki son denetim taşır.  
  
##  <a name="setdefid"></a>CDialog::SetDefID  
 Bir iletişim kutusu için varsayılan basma düğmesi denetimi değiştirir.  
  
```  
void SetDefID(UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `nID`  
 Varsayılan olacak basma düğmesi denetiminin Kimliğini belirtir.  
  
##  <a name="sethelpid"></a>CDialog::SetHelpID  
 İletişim kutusu için bir bağlama duyarlı Yardım kimlik ayarlar.  
  
```  
void SetHelpID(UINT nIDR);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIDR*  
 Bağlama duyarlı Yardım kimliğini belirtir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek DLGCBR32](../../visual-cpp-samples.md)   
 [MFC örnek DLGTEMPL](../../visual-cpp-samples.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

