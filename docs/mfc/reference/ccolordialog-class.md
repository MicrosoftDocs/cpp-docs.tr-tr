---
title: CColorDialog sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CColorDialog
- AFXDLGS/CColorDialog
- AFXDLGS/CColorDialog::CColorDialog
- AFXDLGS/CColorDialog::DoModal
- AFXDLGS/CColorDialog::GetColor
- AFXDLGS/CColorDialog::GetSavedCustomColors
- AFXDLGS/CColorDialog::SetCurrentColor
- AFXDLGS/CColorDialog::OnColorOK
- AFXDLGS/CColorDialog::m_cc
dev_langs:
- C++
helpviewer_keywords:
- CColorDialog [MFC], CColorDialog
- CColorDialog [MFC], DoModal
- CColorDialog [MFC], GetColor
- CColorDialog [MFC], GetSavedCustomColors
- CColorDialog [MFC], SetCurrentColor
- CColorDialog [MFC], OnColorOK
- CColorDialog [MFC], m_cc
ms.assetid: d013dc25-9290-4b5d-a97e-95ad7208e13b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3888f054baab61bb7422403b0766d7f757914d1d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357988"
---
# <a name="ccolordialog-class"></a>CColorDialog sınıfı
Bir renk seçimi iletişim kutusunu uygulamanıza eklemenizi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CColorDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CColorDialog::CColorDialog](#ccolordialog)|Oluşturan bir `CColorDialog` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CColorDialog::DoModal](#domodal)|Renk iletişim kutusu görüntüler ve bir seçim yapmasına olanak tanır.|  
|[CColorDialog::GetColor](#getcolor)|Döndürür bir **COLORREF** seçili renk değerleri içeren yapısı.|  
|[CColorDialog::GetSavedCustomColors](#getsavedcustomcolors)|Kullanıcı tarafından oluşturulan özel renkler alır.|  
|[CColorDialog::SetCurrentColor](#setcurrentcolor)|Belirtilen renk geçerli renk seçimi zorlar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CColorDialog::OnColorOK](#oncolorok)|İletişim kutusuna girilen renk doğrulamak için geçersiz kılın.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CColorDialog::m_cc](#m_cc)|İletişim kutusu ayarlarını özelleştirmek için kullanılan yapısı.|  
  
## <a name="remarks"></a>Açıklamalar  
 A `CColorDialog` nesne için görüntü sistem tanımlı renklerin listesini içeren bir iletişim kutusu değil. Kullanıcı seçin veya belirli bir renk iletişim kutusu çıktığında, ardından uygulamayı geri bildirilir listeden oluşturun.  
  
 Oluşturmak için bir `CColorDialog` nesnesi, sağlanan bir oluşturucu kullanın veya yeni bir sınıf türetin ve kendi özel Oluşturucu kullanın.  
  
 İletişim kutusu oluşturulan sonra ayarlamak veya herhangi bir değer değiştirmek [m_cc](#m_cc) yapısı, iletişim kutusunun denetimlerinin değerlerini başlatılamadı. `m_cc` Yapısıdır türü [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830).  
  
 İletişim kutusunun denetimleri başlatma sonra çağrı `DoModal` üye işlevi iletişim kutusunu görüntülemek ve kullanıcının bir renk seçmesine izin vermek için. `DoModal` iletişim kutusunun Tamam ya da kullanıcının seçimini döndürür ( **IDOK**) veya iptal ( **IDCANCEL**) düğmesi.  
  
 Varsa `DoModal` döndürür **IDOK**, aşağıdakilerden birini kullanabilirsiniz `CColorDialog`ait kullanıcı tarafından giriş bilgilerini almak için üye işlevleri.  
  
 Windows kullanabilirsiniz [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) işlevi iletişim kutusunu başlatma sırasında bir hata olup olmadığını belirlemek ve hata hakkında daha fazla bilgi için.  
  
 `CColorDialog` üzerinde COMMDLG kullanır. Windows 3.1 ve sonraki sürümleri ile birlikte gelen DLL dosyası.  
  
 Özelleştir iletişim kutusu için bir sınıf türetin `CColorDialog`, özel iletişim şablonu sağlayın ve genişletilmiş denetimlerden bildirim iletilerini işlemek için ileti eşlemesi ekleyin. İşlenmemiş tüm iletiler için temel sınıf geçirilmesi gerekir.  
  
 Kanca işlevini özelleştirme gerekli değildir.  
  
> [!NOTE]
>  Bazı yüklemeler üzerinde `CColorDialog` nesne diğer yapmak için framework kullandıysanız, gri arka plan görüntülemez `CDialog` nesneleri gri.  
  
 Kullanma hakkında daha fazla bilgi için `CColorDialog`, bkz: [ortak iletişim kutusu sınıfları](../../mfc/common-dialog-classes.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CColorDialog`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdlgs.h  
  
##  <a name="ccolordialog"></a>  CColorDialog::CColorDialog  
 Oluşturan bir `CColorDialog` nesnesi.  
  
```  
CColorDialog(
    COLORREF clrInit = 0,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *clrInit*  
 Varsayılan renk seçimi. Herhangi bir değer belirtilirse, RGB(0,0,0) (siyah) varsayılandır.  
  
 `dwFlags`  
 İletişim kutusunun görünümünü ve işlevini Özelleştir bayrakları kümesi. Daha fazla bilgi için bkz: [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830) Windows SDK'sındaki yapısı.  
  
 `pParentWnd`  
 İletişim kutusunun üst veya sahibi penceresi için bir işaretçi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#49](../../mfc/codesnippet/cpp/ccolordialog-class_1.cpp)]  
  
##  <a name="domodal"></a>  CColorDialog::DoModal  
 Windows ortak renk iletişim kutusu görüntüler ve kullanıcının bir renk seçmesine izin vermek için bu işlevini çağırın.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **IDOK** veya **IDCANCEL**. Varsa **IDCANCEL** olan döndürülen Windows çağrısı [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) işlevi bir hata oluşup oluşmadığını belirleyin.  
  
 **IDOK** ve **IDCANCEL** kullanıcı Tamam'ı veya iptal düğmesine seçili olmadığını gösterecek sabittir.  
  
### <a name="remarks"></a>Açıklamalar  
 Üyeleri ayarlayarak çeşitli renk iletişim kutusu seçenekleri başlatmak istiyorsanız [m_cc](#m_cc) yapısı, çağırmadan önce yapmalısınız `DoModal` ancak iletişim kutusu nesnesi oluşturulur.  
  
 Çağırdıktan sonra `DoModal`, diğer üye ayarları veya kullanıcı tarafından bilgi giriş iletişim kutusuna almak için işlevleri çağırabilir.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CColorDialog::CColorDialog](#ccolordialog).  
  
##  <a name="getcolor"></a>  CColorDialog::GetColor  
 Bu işlev çağrısı çağrıldıktan sonra `DoModal` seçilen kullanıcıya rengi hakkında bilgi almak için.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) değeri renk iletişim kutusunda seçili renk RGB bilgilerini içerir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#50](../../mfc/codesnippet/cpp/ccolordialog-class_2.cpp)]  
  
##  <a name="getsavedcustomcolors"></a>  CColorDialog::GetSavedCustomColors  
 `CColorDialog` nesneleri en fazla 16 özel renkler tanımlamak için renk seçme ek olarak kullanıcı izin verir.  
  
```  
static COLORREF* PASCAL GetSavedCustomColors();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı tarafından oluşturulan özel renkler depolar 16 RGB renk değerleri dizisi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetSavedCustomColors` Üye işlevi bu renkleri erişim sağlar. Sonra bu renkleri alınabilir [DoModal](#domodal) döndürür **IDOK**.  
  
 Her döndürülen dizideki 16 RGB değerleri RGB(255,255,255) (beyaz) başlatıldı. Kullanıcı tarafından seçilen özel renkler, yalnızca uygulama içinde iletişim kutusu çağrılarını arasında kaydedilir. Bu renk çağrılarını uygulamanın arasında kaydetmek istiyorsanız, bunları bazı diğer biçimde gibi bir başlatma kaydetmeniz gerekir (. INI) dosyası.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#51](../../mfc/codesnippet/cpp/ccolordialog-class_3.cpp)]  
  
##  <a name="m_cc"></a>  CColorDialog::m_cc  
 Türü yapısını [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830), özellikleri ve değerlerini iletişim kutusunun üyeleri depolamak.  
  
```  
CHOOSECOLOR m_cc;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturma sonrasında bir `CColorDialog` nesne kullanabileceğiniz `m_cc` çağırmadan önce iletişim kutusu çeşitli yönlerini ayarlamak için [DoModal](#domodal) üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#53](../../mfc/codesnippet/cpp/ccolordialog-class_4.cpp)]  
  
##  <a name="oncolorok"></a>  CColorDialog::OnColorOK  
 İletişim kutusuna girilen renk doğrulamak için geçersiz kılın.  
  
```  
virtual BOOL OnColorOK();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İletişim kutusu değil kapatıldığında, sıfır olmayan; Girilen rengi kabul etmek için 0 Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Renk iletişim kutusunda kullanıcının seçtiği rengin özel doğrulama sağlamak istiyorsanız bu işlev geçersiz kılar.  
  
 Kullanıcı bir renk aşağıdaki iki yöntemden birini seçebilirsiniz:  
  
-   Renk paleti üzerinde renk'yı tıklatın. Seçilen rengin RGB değerleri, ardından uygun RGB düzenleme kutularına yansıtılır.  
  
-   RGB girme değerleri kutuları Düzenle  
  
 Geçersiz kılma `OnColorOK` kullanıcının girdiği ortak bir renk iletişim kutusu için herhangi bir uygulamaya özgü nedenle renk Reddet olanak tanır.  
  
 Normalde, çünkü framework renkleri varsayılan doğrulanmasını sağlar ve geçersiz bir renk girdiyseniz bir ileti kutusu görüntüler bu işlevi kullanmak gerekmez.  
  
 Çağırabilirsiniz [SetCurrentColor](#setcurrentcolor) içinden `OnColorOK` renk seçimi zorlamak için. Bir kez `OnColorOK` çalıştırılmış (diğer bir deyişle, kullanıcı **Tamam** renk değişikliği kabul etmek için), çağırabilirsiniz [GetColor](#getcolor) yeni renk RGB değerini almak için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#52](../../mfc/codesnippet/cpp/ccolordialog-class_5.cpp)]  
  
##  <a name="setcurrentcolor"></a>  CColorDialog::SetCurrentColor  
 Bu işlev çağrısı çağrıldıktan sonra `DoModal` belirtilen renk değeri geçerli renk seçimi zorlamak için `clr`.  
  
```  
void SetCurrentColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Parametreler  
 `clr`  
 RGB renk değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev içinde ileti işleyicisi çağrılır veya `OnColorOK`. İletişim kutusu, kullanıcının seçimini değerine göre otomatik olarak güncelleştirecektir `clr` parametresi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CColorDialog::OnColorOK](#oncolorok).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek MDI](../../visual-cpp-samples.md)   
 [MFC örnek DRAWCLI](../../visual-cpp-samples.md)   
 [CCommonDialog sınıfı](../../mfc/reference/ccommondialog-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

