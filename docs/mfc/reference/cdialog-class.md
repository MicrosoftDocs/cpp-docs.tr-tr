---
title: CDialog sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: d3c3bca7932b9e9c7e7723b286c83ca3694a9968
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57305100"
---
# <a name="cdialog-class"></a>CDialog sınıfı

İletişim kutularını ekranda görüntülemek için kullanılan taban sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CDialog : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDialog::CDialog](#cdialog)|Oluşturur bir `CDialog` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDialog::Create](#create)|Başlatır `CDialog` nesne. Modsuz iletişim kutusu oluşturur ve ona ekler `CDialog` nesne.|
|[CDialog::CreateIndirect](#createindirect)|(Değil kaynak tabanlı) bellekteki bir iletişim kutusu şablonundan modsuz iletişim kutusu oluşturur.|
|[CDialog::DoModal](#domodal)|Kalıcı bir iletişim kutusu çağırır ve işiniz bittiğinde döndürür.|
|[CDialog::EndDialog](#enddialog)|Kalıcı bir iletişim kutusu kapanır.|
|[CDialog::GetDefID](#getdefid)|Bir iletişim kutusu için varsayılan pushbutton denetim Kimliğini alır.|
|[CDialog::GotoDlgCtrl](#gotodlgctrl)|Odağı bir iletişim kutusu belirtilen iletişim kutusu denetiminde taşır.|
|[CDialog::InitModalIndirect](#initmodalindirect)|(Değil kaynak tabanlı) bellekteki bir iletişim kutusu şablonundan kalıcı bir iletişim kutusu oluşturur. Parametreleri işlevi kadar saklanır `DoModal` çağrılır.|
|[CDialog::MapDialogRect](#mapdialogrect)|İletişim kutusu birimleri bir dikdörtgen ekran birimlerine dönüştürür.|
|[CDialog::NextDlgCtrl](#nextdlgctrl)|Odağı sonraki iletişim kutusu denetim iletişim kutusuna taşır.|
|[CDialog::OnInitDialog](#oninitdialog)|İletişim kutusu başlatıcısını büyütmek için geçersiz kılın.|
|[CDialog::OnSetFont](#onsetfont)|Bir iletişim kutusu denetimi metin çizer yapılırken kullanılacak olan yazı tipi belirtmek için geçersiz kılın.|
|[CDialog::PrevDlgCtrl](#prevdlgctrl)|Odağı önceki iletişim kutusunda iletişim kutusu denetimi taşır.|
|[CDialog::SetDefID](#setdefid)|Varsayılan pushbutton denetim için bir iletişim kutusu belirtilen ı pushbutton olarak değiştirir.|
|[CDialog::SetHelpID](#sethelpid)|İletişim kutusu için bağlama duyarlı Yardım bir kimlik ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDialog::OnCancel](#oncancel)|İptal düğmesi ya da ESC anahtar eylemi gerçekleştirmek için geçersiz kılın. Varsayılan iletişim kutusu kapanır ve `DoModal` IDCANCEL döndürür.|
|[CDialog::OnOK](#onok)|Kalıcı iletişim kutusunda Tamam düğmesi eylemi gerçekleştirmek için geçersiz kılın. Varsayılan iletişim kutusu kapanır ve `DoModal` IDOK döndürür.|

## <a name="remarks"></a>Açıklamalar

İletişim kutusu, iki tür vardır: kalıcı ve kalıcı olmayan. Uygulama devam etmeden önce kalıcı bir iletişim kutusu kullanıcı tarafından kapatılması gerekir. İletişim kutusunu görüntülemek ve başka bir görevi iptal etme veya iletişim kutusu kaldırma döndürmek kullanıcının modsuz iletişim kutusu sağlar.

A `CDialog` nesne bir iletişim şablonunu bileşimidir ve bir `CDialog`-türetilmiş sınıf. İletişim şablonu oluşturmak ve bir kaynak olarak depolamak için iletişim kutusu düzenleyicisini kullanın ve ardından türetilen bir sınıf oluşturmak için Sınıf Ekle sihirbazını kullanmak `CDialog`.

Diğer pencere gibi bir iletişim kutusu Windows iletileri alır. Bir iletişim kutusunda, iletişim kutusunun denetimlerden bildirim iletilerini işleme, kullanıcının, iletişim kutusu ile nasıl etkileştiğini olduğundan özellikle ilgilendiğiniz. Seçmek istediğiniz iletileri tanıtıcısı ve ileti işleyicisi üye işlevleri ve uygun ileti eşlemesi girişleri sınıfı, ekler için Özellikler penceresini kullanın. Yalnızca işleyici üye işlevlerde uygulamaya özgü kod yazmanız gerekir.

İsterseniz, her zaman ileti eşlemesi girişleri ve üye işlevleri el ile yazabilirsiniz.

Tüm ortamlarda en basit iletişim kutusu, üye değişkenleri iletişim kutusunun denetimlerinde kullanıcı tarafından girilen verileri depolamak için veya kullanıcı için verileri görüntülemek için türetilmiş iletişim sınıfınızı ekleyin. Üye değişkenleri oluşturmak ve bunları denetimleri ile ilişkilendirmek için değişken Ekle Sihirbazı'nı kullanabilirsiniz. Aynı zamanda, bir değişken türü ve izin verilen her bir değişken için değer aralığını seçin. Kod Sihirbazı'nı türetilmiş iletişim sınıfınızı üye değişkenleri ekler.

Üye değişkenleri ve iletişim kutusunun denetimleri arasında veri alışverişi otomatik olarak işlemek için bir veri eşleme oluşturulur. Veri eşlemesi uygun değerlerle iletişim kutusundaki denetimler başlatmak, verileri almak ve veri doğrulama işlevleri sağlar.

Kalıcı bir iletişim kutusu oluşturmak için türetilmiş bir iletişim kutusu sınıfı için oluşturucu kullanılarak yığındaki bir nesne oluşturmak ve sonra çağrı `DoModal` iletişim kutusu penceresine ve denetimlerini oluşturmak için. Kalıcı olmayan iletişim kutusu oluşturmak istiyorsanız, çağrı `Create` iletişim sınıfınızı oluşturucusunun içinde.

Kullanarak bellekte bir şablon oluşturabilirsiniz bir [DLGTEMPLATE](/windows/desktop/api/winuser/ns-winuser-dlgtemplate) veri Windows SDK içinde anlatıldığı gibi yapılandırın. Oluşturun, sonra bir `CDialog` nesne, çağrı [CreateIndirect](#createindirect) bir geçici oluşturma iletişim kutusu veya çağrı [InitModalIndirect](#initmodalindirect) ve [DoModal](#domodal) kalıcı bir oluşturmak için iletişim kutusu.

Veri Değişimi ve doğrulaması eşlemesi içinde geçersiz kılma yazılır `CWnd::DoDataExchange` yeni iletişim sınıfınıza eklenir. Bkz: [DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange) üye işlevinde `CWnd` değişimi ve doğrulaması işlevselliği hakkında daha fazla bilgi için.

Programcı hem de çerçeve çağrı `DoDataExchange` dolaylı olarak yapılan bir çağrıyla [CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata).

Framework çağrıları `UpdateData` kullanıcı bir kalıcı iletişim kutusunu kapatmak için Tamam düğmesine tıkladığında. (İptal düğmesine tıkladıysanız verileri alınamadı.) Varsayılan uygulaması [OnInitDialog](#oninitdialog) de çağırır `UpdateData` denetimleri ilk değerleri ayarlamak için. Genellikle geçersiz kılma `OnInitDialog` daha fazla denetim başlatılamadı. `OnInitDialog` Tüm iletişim kutusu denetimleri oluşturulur ve hemen önce iletişim kutusu görüntülenir. sonra çağrılır.

Çağırabilirsiniz `CWnd::UpdateData` kalıcı veya geçici bir iletişim kutusu yürütülmesi sırasında herhangi bir zamanda.

El ile geliştirdiğiniz bir iletişim kutusu, gerekli üye değişkenleri iletişim kutusu türetilmiş sınıf için kendiniz eklemeniz ve ayarlayın veya bu değerleri almak için üye işlevleri ekleyin.

Kullanıcı Tamam'ı veya İptal düğmeleri bastığında veya kodunuzu çağırdığında kalıcı bir iletişim kutusu kapanır `EndDialog` üye işlevi.

Her zaman modsuz iletişim kutusu uyguladığınızda, geçersiz kılma `OnCancel` üye işleve ve çağrı `DestroyWindow` gelen içindeki. Temel sınıfı çağırmayın `CDialog::OnCancel`çağırır çünkü `EndDialog`, iletişim kutusunda görünmez hale getirir, ancak bunu yok etmez. Geçersiz kılmalıdır `PostNcDestroy` silinmesi için kalıcı olmayan iletişim kutuları için **bu**, kalıcı olmayan iletişim kutuları genellikle ile ayrılmış olduğundan **yeni**. Kalıcı iletişim kutuları karesinde genellikle oluşturulur ve gerekmeyen `PostNcDestroy` temizleme.

Daha fazla bilgi için `CDialog`, bkz: [iletişim kutuları](../../mfc/dialog-boxes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CDialog`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="cdialog"></a>  CDialog::CDialog

Kaynak tabanlı kalıcı bir iletişim kutusu oluşturmak için oluşturucu genel biçimindeki çağırın.

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

*lpszTemplateName*<br/>
Bir iletişim kutusu şablonu kaynak adı null ile sonlandırılmış bir dize içerir.

*nIDTemplate*<br/>
Bir iletişim kutusu şablon kaynağı kimliği numarasını içerir.

*pParentWnd*<br/>
Üst veya sahibi pencere nesnesi için işaret (tür [CWnd](../../mfc/reference/cwnd-class.md)) ait olduğu iletişim nesnesi. NULL ise, ana uygulama penceresini iletişim nesnenin üst penceresine ayarlanır.

### <a name="remarks"></a>Açıklamalar

Oluşturucunun bir form şablon adına göre iletişim kaynağına erişim sağlar. Diğer Oluşturucu erişim şablonu kimliği numarasıyla genellikle sağlar bir **IDD_** önek (örneğin, IDD_DIALOG1).

Bellekte bir şablondan kalıcı bir iletişim kutusu oluşturmak için öncelikle parametresiz, korumalı oluşturucusunu çağırır ve ardından çağırın `InitModalIndirect`.

Yukarıdaki yöntemlerden biri ile kalıcı bir iletişim kutusu oluşturduktan sonra çağrı `DoModal`.

Modsuz iletişim kutusu oluşturmak için korumalı biçimini kullanın. `CDialog` Oluşturucusu. Oluşturucu modsuz iletişim kutusu uygulamak için kendi iletişim kutusu sınıfı türetilmesi gerekir çünkü korunur. Yapı modsuz iletişim kutusu iki adımlı bir işlemdir. İlk Oluşturucu çağırın. ardından çağırın `Create` üye işlevi bir kaynak tabanlı iletişim kutusu oluşturma veya çağrı `CreateIndirect` bellekte bir şablondan Oluştur iletişim kutusu için.

##  <a name="create"></a>  CDialog::Create

Çağrı `Create` kullanarak bir kaynak iletişim kutusu şablonundan modsuz iletişim kutusu oluşturmak için.

```
virtual BOOL Create(
    LPCTSTR lpszTemplateName,
    CWnd* pParentWnd = NULL);

virtual BOOL Create(
    UINT nIDTemplate,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszTemplateName*<br/>
Bir iletişim kutusu şablonu kaynak adı null ile sonlandırılmış bir dize içerir.

*pParentWnd*<br/>
Üst pencere nesneye işaret (tür [CWnd](../../mfc/reference/cwnd-class.md)) ait olduğu iletişim nesnesi. NULL ise, ana uygulama penceresini iletişim nesnenin üst penceresine ayarlanır.

*nIDTemplate*<br/>
Bir iletişim kutusu şablon kaynağı kimliği numarasını içerir.

### <a name="return-value"></a>Dönüş Değeri

Her iki biçimi iletişim kutusu oluşturma ve başlatma başarılı olursa sıfır döndürür; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Çağrı yerleştirmek `Create` Oluşturucusu veya çağrı içinde Oluşturucu sonra çağrılır.

İki tür `Create` üye işlevi sağlanan erişim iletişim kutusu şablon kaynağı için şablon adı veya şablon kimliği numarasını (örneğin, IDD_DIALOG1).

Ya da formun üst pencere nesnesi için bir işaretçi geçirin. Varsa *pParentWnd* null, iletişim kutusu, ana uygulama penceresini ayarlamak, üst veya sahibi penceresi ile oluşturulur.

`Create` İletişim kutusu oluşturur hemen sonra üye işlevi döndürür.

Üst pencere oluşturulurken iletişim kutusu görüntülendiğinde iletişim kutusu şablonunda ws_vısıble stili kullanın. Aksi takdirde, çağırmalıdır `ShowWindow`. Daha fazla iletişim kutusu stilleri ve bunların uygulama için bkz [DLGTEMPLATE](/windows/desktop/api/winuser/ns-winuser-dlgtemplate) Windows SDK yapısı ve [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) içinde *MFC başvurusu*.

Kullanım `CWnd::DestroyWindow` işlevi tarafından oluşturulan bir iletişim kutusu yok edilecek `Create` işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#62](../../mfc/codesnippet/cpp/cdialog-class_1.cpp)]

##  <a name="createindirect"></a>  CDialog::CreateIndirect

Bellekteki bir iletişim kutusu şablonundan modsuz iletişim kutusu oluşturmak için bu üye işlevini çağırın.

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

*lpDialogTemplate*<br/>
İletişim kutusu oluşturmak için kullanılan bir iletişim kutusu şablonu içeren bellek işaret eder. Bu şablon biçiminde olan bir [DLGTEMPLATE](/windows/desktop/api/winuser/ns-winuser-dlgtemplate) yapısı ve denetim bilgileri, Windows SDK içinde açıklandığı gibi.

*pParentWnd*<br/>
İşaret iletişim nesnenin üst pencere nesnesi için (tür [CWnd](../../mfc/reference/cwnd-class.md)). NULL ise, ana uygulama penceresini iletişim nesnenin üst penceresine ayarlanır.

*lpDialogInit*<br/>
DLGINIT kaynağa işaret eder.

*hDialogTemplate*<br/>
Genel bellek içeren bir iletişim kutusunda şablon için bir tanıtıcı içerir. Bu şablon biçiminde olan bir `DLGTEMPLATE` yapısı ve iletişim kutusunda her denetim için verileri.

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu oluşturulur ve başarıyla başlatılmış olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

`CreateIndirect` İletişim kutusu oluşturur hemen sonra üye işlevi döndürür.

Üst pencere oluşturulurken iletişim kutusu görüntülendiğinde iletişim kutusu şablonunda ws_vısıble stili kullanın. Aksi takdirde, çağırmalıdır `ShowWindow` görünmesine neden olacak. Nasıl şablonda diğer iletişim kutusu stilleri belirtebilirsiniz. daha fazla bilgi için bkz: [DLGTEMPLATE](/windows/desktop/api/winuser/ns-winuser-dlgtemplate) Windows SDK'sındaki yapısı.

Kullanım `CWnd::DestroyWindow` işlevi tarafından oluşturulan bir iletişim kutusu yok edilecek `CreateIndirect` işlevi.

ActiveX denetimleri içeren iletişim kutuları DLGINIT kaynakta sağlanan ek bilgiler sağlamanız gerekir.

##  <a name="domodal"></a>  CDialog::DoModal

Kalıcı bir iletişim kutusu çağırma ve işiniz bittiğinde iletişim kutusu sonucu döndürmek için bu üye işlevini çağırın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

Bir **int** değerini belirten bir değer *Nsonuç* için geçirilen parametre [CDialog::EndDialog](#enddialog) iletişim kutusunu kapatmak için kullanılan üye işlevi. Dönüş değeri başka bir hata oluştu, çıkış penceresi hata bilgileri içerir ve bu durumda, işlev iletişim kutusu veya IDABORT oluşturulamadı -1 ise [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360).

### <a name="remarks"></a>Açıklamalar

İletişim kutusu etkin olduğu sırada bu üye işlevi, tüm kullanıcı etkileşim işler. Bu iletişim kutusu kalıcı olmasını sağlayan nedir, diğer bir deyişle, kullanıcı iletişim kutusu kapatılana kadar diğer windows ile etkileşime giremezler.

Kullanıcı bir iletişim kutusunda Tamam'ı veya İptal'i, bir ileti işleyicisi üye işlevi gibi pushbuttons gibi tıklarsa [OnOK](#onok) veya [OnCancel](#oncancel), iletişim kutusunu kapatmak adı verilir. Varsayılan `OnOK` üye işlevi Doğrula iletişim kutusu verileri güncelleştirmek ve varsayılan kapatıp sonucu IDOK iletişim kutusuyla `OnCancel` üye işlevi, sonuç IDCANCEL iletişim kutusu kapatılır, doğrulama veya güncelleştirme iletişim kutusu verileri. Davranışları değiştirmek için bu ileti işleyici işlevleri geçersiz kılabilirsiniz.

> [!NOTE]
> `PreTranslateMessage` Şimdi, kalıcı bir iletişim kutusu ileti işleme için çağrılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#63](../../mfc/codesnippet/cpp/cdialog-class_2.cpp)]

##  <a name="enddialog"></a>  CDialog::EndDialog

Kalıcı bir iletişim kutusu sonlandırmak için bu üye işlevini çağırın.

```
void EndDialog(int nResult);
```

### <a name="parameters"></a>Parametreler

*Nsonuç*<br/>
Çağırana iletişim kutusundan döndürülecek değeri içeren `DoModal`.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevinin döndürdüğü *Nsonuç* dönüş değeri olarak `DoModal`. Kullanmalısınız `EndDialog` kalıcı bir iletişim kutusu oluşturulduğunda işlemeyi tamamlamak için işlevi.

Çağırabilirsiniz `EndDialog` herhangi bir zamanda bile içinde [OnInitDialog](#oninitdialog), kapatın, bu durumda, önce iletişim kutusu gösterilir veya giriş odağını ayarlanmadan önce.

`EndDialog` iletişim kutusunun hemen kapatmaz. Bunun yerine, geçerli ileti işleyicisini döndürür olarak kapatmak için iletişim kutusu yönlendiren bir bayrak ayarlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#64](../../mfc/codesnippet/cpp/cdialog-class_3.cpp)]

[!code-cpp[NVC_MFCControlLadenDialog#65](../../mfc/codesnippet/cpp/cdialog-class_4.cpp)]

##  <a name="getdefid"></a>  CDialog::GetDefID

Çağrı `GetDefID` varsayılan pushbutton denetiminin kimliği için bir iletişim kutusu almak için üye işlevi.

```
DWORD GetDefID() const;
```

### <a name="return-value"></a>Dönüş Değeri

32-bit bir değer ( `DWORD`). Varsayılan basma düğmesi kimliği değeri varsa, dwpoint DC_HASDEFID ve düşük düzey sözcük kimliği değerini içerir. Varsayılan basma düğmesi kimliğe sahip değilse, dönüş değeri 0'dır.

### <a name="remarks"></a>Açıklamalar

Tamam düğmesi genellikle budur.

##  <a name="gotodlgctrl"></a>  CDialog::GotoDlgCtrl

İletişim kutusunda belirtilen denetim odağı taşır.

```
void GotoDlgCtrl(CWnd* pWndCtrl);
```

### <a name="parameters"></a>Parametreler

*pWndCtrl*<br/>
Odağı alacak penceresi (Denetim) tanımlar.

### <a name="remarks"></a>Açıklamalar

(Olarak geçirmek için alt pencere) denetlemek için bir işaretçi almaya *pWndCtrl*, çağrı `CWnd::GetDlgItem` bir işaretçi döndüren üye işlevi bir [CWnd](../../mfc/reference/cwnd-class.md) nesne.

### <a name="example"></a>Örnek

  Örneğin bakın [CWnd::GetDlgItem](../../mfc/reference/cwnd-class.md#getdlgitem).

##  <a name="initmodalindirect"></a>  CDialog::InitModalIndirect

Bellekte oluşturmak bir iletişim kutusu şablonu kullanarak bir kalıcı iletişim kutusu nesnesini başlatmak için bu üye işlevini çağırın.

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

*lpDialogTemplate*<br/>
İletişim kutusu oluşturmak için kullanılan bir iletişim kutusu şablonu içeren bellek işaret eder. Bu şablon biçiminde olan bir [DLGTEMPLATE](/windows/desktop/api/winuser/ns-winuser-dlgtemplate) yapısı ve denetim bilgileri, Windows SDK içinde açıklandığı gibi.

*hDialogTemplate*<br/>
Genel bellek içeren bir iletişim kutusunda şablon için bir tanıtıcı içerir. Bu şablon biçiminde olan bir `DLGTEMPLATE` yapısı ve iletişim kutusunda her denetim için verileri.

*pParentWnd*<br/>
Üst veya sahibi pencere nesnesi için işaret (tür [CWnd](../../mfc/reference/cwnd-class.md)) ait olduğu iletişim nesnesi. NULL ise, ana uygulama penceresini iletişim nesnenin üst penceresine ayarlanır.

*lpDialogInit*<br/>
DLGINIT kaynağa işaret eder.

### <a name="return-value"></a>Dönüş Değeri

İletişim nesnesi oluşturulur ve başarıyla başlatılmış olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Dolaylı olarak kalıcı bir iletişim kutusu oluşturmak için önce genel bir bellek bloğunu ayırmak ve iletişim kutusu şablonu ile doldurun. Boş'ı çağırın `CDialog` iletişim kutusu nesneyi oluşturmak için oluşturucu. Ardından, arama `InitModalIndirect` bellek içi iletişim kutusu şablona, işlemeyi saklamak için. Windows iletişim kutusu oluşturulur ve görüntülenir daha sonra zaman [DoModal](#domodal) üye işlevi çağrılır.

ActiveX denetimleri içeren iletişim kutuları DLGINIT kaynakta sağlanan ek bilgiler sağlamanız gerekir.

##  <a name="mapdialogrect"></a>  CDialog::MapDialogRect

İletişim kutusu birimleri bir dikdörtgen ekran birimine dönüştürmek için çağırın.

```
void MapDialogRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
İşaret eden bir [RECT](/windows/desktop/api/windef/ns-windef-tagrect) yapısı veya [CRect](../../atl-mfc-shared/reference/crect-class.md) iletişim kutusu içeren nesne koordinatları dönüştürülecek.

### <a name="remarks"></a>Açıklamalar

İletişim kutusu birimleri cinsinden ortalama genişlik ve yükseklik yazı tipi iletişim kutusu metni için kullanılan karakter türetilen geçerli iletişim kutusu temel birim belirtilmiştir. Tek bir yatay birim dörtte biri iletişim kutusu genişliği temel birim, ve dikey bir birimi bir sekizinci iletişim kutusu temel yükseklik birimi.

`GetDialogBaseUnits` Windows işlevi sistem yazı tipi boyutu bilgilerini döndürür, ancak kaynak tanımı dosyasında DS_SETFONT stili kullanırsanız her iletişim kutusu için farklı bir yazı tipi belirtebilirsiniz. `MapDialogRect` Windows işlevi, bu iletişim kutusu için uygun yazı tipini kullanır.

`MapDialogRect` Üye işlevini değiştiren iletişim kutusu birimlerinde *lpRect* ile dikdörtgen Oluştur iletişim kutusu veya bir kutu içinde bir denetim konumlandırmak için kullanılabilir, böylece ekran birimleri (piksel cinsinden).

##  <a name="nextdlgctrl"></a>  CDialog::NextDlgCtrl

İletişim kutusunda sonraki denetim odağı taşır.

```
void NextDlgCtrl() const;
```

### <a name="remarks"></a>Açıklamalar

Odak en son denetim iletişim kutusunda, ilk denetime taşır.

##  <a name="oncancel"></a>  CDialog::OnCancel

Kullanıcı tıkladığında framework bu yöntemi çağırır **iptal** veya kalıcı veya geçici bir iletişim kutusu, ESC tuşuna basar.

```
virtual void OnCancel();
```

### <a name="remarks"></a>Açıklamalar

(Eski verilerin geri yüklenmesi gibi) eylemleri gerçekleştirmek için bu yöntemi yok sayın kullanıcı kapattığı zaman iletişim kutusunu tıklatarak **iptal** veya ESC tuşuna basarak. Varsayılan çağırarak kalıcı bir iletişim kutusu kapanır [EndDialog](#enddialog) ve neden [DoModal](#domodal) IDCANCEL döndürülecek.

Uygularsanız **iptal** düğmesi modsuz iletişim kutusu içinde geçersiz kılmanız gerekir `OnCancel` yöntemi ve çağrı [DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) içindeki. Temel sınıf yöntemini çağırır çünkü çağırmayın `EndDialog`, hangi iletişim kutusu görünmez yapma ancak yok değil.

> [!NOTE]
>  Kullandığınızda, bu yöntemi geçersiz kılınamıyor bir `CFileDialog` altında Windows XP derlenmiş bir program nesnesi. Hakkında daha fazla bilgi için `CFileDialog`, bkz: [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#66](../../mfc/codesnippet/cpp/cdialog-class_5.cpp)]

##  <a name="oninitdialog"></a>  CDialog::OnInitDialog

Yanıt olarak bu yöntem çağrılır `WM_INITDIALOG` ileti.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulama giriş odağını denetimlerden birini iletişim kutusuna olup olmadığını belirtir. Varsa `OnInitDialog` sıfır döndürür, Windows ayarlar giriş odağını ilk denetim iletişim kutusunda varsayılan konumu. Uygulama, yalnızca açıkça giriş odağını denetimlerden birini iletişim kutusuna ayarlarsanız 0 geri dönebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Windows gönderir `WM_INITDIALOG` sırasında iletişim kutusu için ileti [Oluştur](#create), [CreateIndirect](#createindirect), veya [DoModal](#domodal) hemen önce iletişim kutusu ortaya çıkan çağrıları görüntülenir.

İletişim kutusu başlatılırken özel işlem gerçekleştirmek istiyorsanız bu yöntemi yok sayın. Geçersiz kılınan sürümünde temel sınıfı çağırın `OnInitDialog` ancak dönüş değerini yoksayar. Genellikle döndüreceği `TRUE` , geçersiz kılınan yönteminden.

Windows çağrıları `OnInitDialog` tüm Microsoft Foundation Class Kitaplığı iletişim kutuları için ortak bir standart genel iletişim kutusu yordamı kullanarak işlevi. Bu işlev, ileti eşlemesi aracılığıyla çağırmaz ve bu nedenle, bir ileti eşleme girişi için bu yöntem ihtiyacınız yoktur.

> [!NOTE]
> Kullandığınızda, bu yöntemi geçersiz kılınamıyor bir `CFileDialog` Windows Vista veya sonraki işletim sistemleri altında derlenmiş bir program nesnesi. Değişiklikler hakkında daha fazla bilgi için `CFileDialog` altında Windows Vista ve sonraki sürümlerinde, bkz. [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#67](../../mfc/codesnippet/cpp/cdialog-class_6.cpp)]

##  <a name="onok"></a>  CDialog::OnOK

Kullanıcı tıkladığında çağrılır **Tamam** düğme (düğme, bir kimliği IDOK ile).

```
virtual void OnOK();
```

### <a name="remarks"></a>Açıklamalar

Eylemleri gerçekleştirmek için bu yöntemi yok sayın olduğunda **Tamam** düğmesi etkinleştirilir. İletişim kutusu otomatik veri doğrulama ve exchange içeriyorsa, bu yöntem varsayılan uygulaması iletişim kutusu verileri doğrular ve uygulamanızdaki uygun değişkenlerini güncelleştirir.

Uygularsanız **Tamam** düğmesi modsuz iletişim kutusu içinde geçersiz kılmanız gerekir `OnOK` yöntemi ve çağrı [DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) içindeki. Temel sınıf yöntemini çağırır çünkü çağırmayın [EndDialog](#enddialog) iletişim kutusunda görünmez yapar, ancak yok etmez.

> [!NOTE]
>  Kullandığınızda, bu yöntemi geçersiz kılınamıyor bir `CFileDialog` altında Windows XP derlenmiş bir program nesnesi. Hakkında daha fazla bilgi için `CFileDialog`, bkz: [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#68](../../mfc/codesnippet/cpp/cdialog-class_7.cpp)]

##  <a name="onsetfont"></a>  CDialog::OnSetFont

Metni çizerken iletişim kutusu denetim kullanacağı yazı tipini belirtir.

```
Virtual void OnSetFont(CFont* pFont);
```

### <a name="parameters"></a>Parametreler

*pFont*<br/>
[in] Bir işaretçi varsayılan yazı tipini, bu iletişim kutusundaki tüm denetimler için kullanılacak yazı tipini belirtir.

### <a name="remarks"></a>Açıklamalar

İletişim kutusu, tüm denetimler için varsayılan olarak belirtilen yazı tipi kullanın.

İletişim kutusu Düzenleyicisi iletişim kutusu yazı tipi iletişim kutusu şablon kaynağı bir parçası olarak genellikle ayarlar.

> [!NOTE]
> Kullandığınızda, bu yöntemi geçersiz kılınamıyor bir `CFileDialog` Windows Vista veya sonraki işletim sistemleri altında derlenmiş bir program nesnesi. Değişiklikler hakkında daha fazla bilgi için `CFileDialog` altında Windows Vista ve sonraki sürümlerinde, bkz. [CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md).

##  <a name="prevdlgctrl"></a>  CDialog::PrevDlgCtrl

Odağı önceki denetim iletişim kutusundaki ayarlar.

```
void PrevDlgCtrl() const;
```

### <a name="remarks"></a>Açıklamalar

İletişim kutusunu ilk denetim odağı yse son kutuya denetimi taşır.

##  <a name="setdefid"></a>  CDialog::SetDefID

Bir iletişim kutusu varsayılan pushbutton denetimini değiştirir.

```
void SetDefID(UINT nID);
```

### <a name="parameters"></a>Parametreler

*nID*<br/>
Varsayılan olacak pushbutton denetimin Kimliğini belirtir.

##  <a name="sethelpid"></a>  CDialog::SetHelpID

İletişim kutusu için bağlama duyarlı Yardım bir kimlik ayarlar.

```
void SetHelpID(UINT nIDR);
```

### <a name="parameters"></a>Parametreler

*nIDR*<br/>
Bağlama duyarlı Yardım kimliğini belirtir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek DLGCBR32](../../visual-cpp-samples.md)<br/>
[MFC örnek DLGTEMPL](../../visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
