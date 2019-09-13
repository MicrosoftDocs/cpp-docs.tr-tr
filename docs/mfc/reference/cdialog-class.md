---
title: CDialog sınıfı
ms.date: 09/07/2019
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
ms.openlocfilehash: b07190c70fb11950b25aff45fb10e850c0e81b24
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907614"
---
# <a name="cdialog-class"></a>CDialog sınıfı

Ekranda iletişim kutularını görüntülemek için kullanılan temel sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CDialog : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDialog:: CDialog](#cdialog)|Bir `CDialog` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDialog:: Create](#create)|`CDialog` Nesnesini başlatır. Kalıcı olmayan bir iletişim kutusu oluşturur ve `CDialog` nesneye ekler.|
|[CDialog:: Createdolaylı](#createindirect)|Bellekteki iletişim kutusu şablonundan (kaynak tabanlı değil) kalıcı olmayan iletişim kutusu oluşturur.|
|[CDialog::D oModal](#domodal)|Kalıcı bir iletişim kutusu çağırır ve tamamlandığında döndürür.|
|[CDialog:: EndDialog](#enddialog)|Kalıcı iletişim kutusunu kapatır.|
|[CDialog:: Getdeıd](#getdefid)|Bir iletişim kutusu için varsayılan basma düğmesi denetiminin KIMLIĞINI alır.|
|[CDialog:: Sayfaydlctrl](#gotodlgctrl)|Odağı iletişim kutusunda belirtilen iletişim kutusu denetimine kaydırır.|
|[CDialog:: InitModalIndirect](#initmodalindirect)|Bellekteki iletişim kutusu şablonundan (kaynak tabanlı değil) kalıcı iletişim kutusu oluşturur. Parametreler, işlev `DoModal` çağrılana kadar saklanır.|
|[CDialog:: MapDialogRect](#mapdialogrect)|Bir dikdörtgenin iletişim kutusu birimlerini ekran birimlerine dönüştürür.|
|[CDialog:: Nextdlctrl](#nextdlgctrl)|Odağı iletişim kutusunda bir sonraki iletişim kutusu denetimine kaydırır.|
|[CDialog:: OnInitDialog](#oninitdialog)|İletişim kutusu başlatmasını artırmak için geçersiz kılın.|
|[CDialog:: OnSetFont](#onsetfont)|İletişim kutusu denetiminin metin çizdiğinde kullanacağı yazı tipini belirtmek için geçersiz kılın.|
|[CDialog::P revDlgCtrl](#prevdlgctrl)|Odağı iletişim kutusunda önceki iletişim kutusu denetimine kaydırır.|
|[CDialog:: Setdeıd](#setdefid)|Bir iletişim kutusu için varsayılan basma düğmesi denetimini belirtilen bir basma kutusu olarak değiştirir.|
|[CDialog:: SetHelpID](#sethelpid)|İletişim kutusu için bağlama duyarlı bir yardım KIMLIĞI ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDialog:: OnCancel](#oncancel)|Iptal düğmesini veya ESC tuşu eylemini gerçekleştirmek için geçersiz kılın. Varsayılan olarak iletişim kutusu kapanır ve `DoModal` IDCANCEL döndürülür.|
|[CDialog:: OnOK](#onok)|Kalıcı iletişim kutusunda Tamam düğmesi eylemini gerçekleştirmek için geçersiz kılın. Varsayılan olarak iletişim kutusu kapanır ve `DoModal` IDOK döndürülür.|

## <a name="remarks"></a>Açıklamalar

İletişim kutuları iki türden oluşur: kalıcı ve kalıcı. Uygulama devam etmeden önce Kullanıcı tarafından kalıcı iletişim kutusu kapatılmalıdır. Kalıcı olmayan iletişim kutusu, kullanıcının iletişim kutusunu görüntülemesini ve iletişim kutusunu iptal etmeden veya kaldırmadan başka bir göreve geri dönmesini sağlar.

Bir `CDialog` nesne, iletişim kutusu şablonunun `CDialog`ve türetilmiş sınıfın bir birleşimidir. İletişim kutusu şablonunu oluşturmak ve bir kaynakta depolamak için iletişim düzenleyicisini kullanın, ardından ' den `CDialog`türetilmiş bir sınıf oluşturmak için sınıf ekleme Sihirbazı ' nı kullanın.

Diğer herhangi bir pencere gibi bir iletişim kutusu, Windows 'dan iletileri alır. İletişim kutusunda özellikle iletişim kutusunun denetimlerinden gelen bildirim iletilerini, kullanıcının iletişim kutusuyla etkileşime girdiği bu yana işlemek istiyorsunuz. İşlemek istediğiniz iletileri seçmek için [sınıf Sihirbazı](mfc-class-wizard.md) 'nı kullanın ve uygun ileti eşleme girdilerini ve ileti işleyici üye işlevlerini sizin için sınıfa ekler. Yalnızca işleyici üye işlevlerinde uygulamaya özel kod yazmanız gerekir.

İsterseniz ileti eşleme girişlerini ve üye işlevlerini her zaman el ile yazabilirsiniz.

En önemsiz iletişim kutusunda, Kullanıcı tarafından iletişim kutusu denetimlerinde girilen verileri depolamak veya Kullanıcı verilerini göstermek için türetilmiş iletişim sınıfınız için üye değişkenleri eklersiniz. Üye değişkenleri oluşturmak ve bunları denetimlerle ilişkilendirmek için değişken Ekleme Sihirbazı 'nı kullanabilirsiniz. Aynı zamanda, her değişken için bir değişken türü ve izin verilebilir bir değer aralığı seçersiniz. Kod Sihirbazı, üye değişkenlerini türetilmiş iletişim kutusu sınıfınıza ekler.

Üye değişkenleri ve iletişim kutusu denetimleri arasındaki veri değişimini otomatik olarak işlemek için bir veri eşlemi oluşturulur. Veri eşlemi, iletişim kutusundaki denetimleri doğru değerlerle başlatacak, verileri alan ve verileri doğrulayan işlevler sağlar.

Kalıcı bir iletişim kutusu oluşturmak için, türetilmiş iletişim sınıfınız için oluşturucuyu kullanarak yığında bir nesne oluşturun ve ardından iletişim kutusu penceresini ve denetimlerini `DoModal` oluşturmak için öğesini çağırın. Kalıcı olmayan bir iletişim kutusu oluşturmak isterseniz, iletişim kutusu `Create` sınıfınızın oluşturucusunu çağırın.

Ayrıca, Windows SDK bölümünde açıklandığı gibi bir [dltemplate](/windows/win32/api/winuser/ns-winuser-dlgtemplate) veri yapısını kullanarak bellekte bir şablon oluşturabilirsiniz. Bir `CDialog` nesne oluşturduktan sonra, geçici bir iletişim kutusu oluşturmak için [createdolaylı](#createindirect) öğesini çağırın veya kalıcı bir iletişim kutusu oluşturmak için [InitModalIndirect](#initmodalindirect) ve [DoModal](#domodal) ' ı çağırın.

Exchange ve doğrulama veri eşlemi, yeni iletişim sınıfınız sınıfına eklenen üzerine `CWnd::DoDataExchange` bir geçersiz kılma ile yazılır. Exchange ve doğrulama işlevselliği hakkında daha fazla bilgi `CWnd` için ' de [DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange) üye işlevine bakın.

Programcılar ve çerçeve çağrısı `DoDataExchange` , [CWnd:: UpdateData](../../mfc/reference/cwnd-class.md#updatedata)çağrısı aracılığıyla dolaylı olarak yapılır.

Kullanıcı, bir `UpdateData` kalıcı iletişim kutusunu kapatmak için Tamam düğmesine tıkladığında çerçeve çağırır. (Iptal düğmesine tıklandığında veri alınamaz.) [OnInitDialog](#oninitdialog) varsayılan uygulanması, denetimlerin başlangıç değerlerini `UpdateData` ayarlamak için de çağırır. Denetimleri daha fazla `OnInitDialog` başlatmak için genellikle geçersiz kılabilirsiniz. `OnInitDialog`Tüm iletişim kutusu denetimleri oluşturulduktan ve iletişim kutusu görüntülenmeden hemen önce çağrılır.

Kalıcı veya kalıcı `CWnd::UpdateData` olmayan bir iletişim kutusunun yürütülmesi sırasında dilediğiniz zaman çağrı yapabilirsiniz.

El ile bir iletişim kutusu geliştirirseniz, gerekli üye değişkenleri türetilmiş iletişim kutusu sınıfına kendiniz ekler ve bu değerleri ayarlamak ya da almak için üye işlevleri eklersiniz.

Kullanıcı Tamam veya iptal düğmelerine bastığında veya kodunuz `EndDialog` üye işlevini çağırdığında kalıcı iletişim kutusu otomatik olarak kapanır.

Kalıcı olmayan bir iletişim kutusu uyguladığınızda, her zaman `OnCancel` üye işlevini geçersiz kılın ve içinden çağırın. `DestroyWindow` , İletişim kutusunu görünmez hale `CDialog::OnCancel`getirir ancak yok etmez `EndDialog`, çağrı yaptığı için temel sınıfı çağırmayın. Kalıcı olmayan iletişim kutuları `PostNcDestroy` genellikle **Yeni**ile ayrıldığından, **bunu**silebilmek için de kalıcı olmayan iletişim kutuları için geçersiz kılmanız gerekir. Kalıcı iletişim kutuları genellikle çerçevede oluşturulur ve `PostNcDestroy` Temizleme gerektirmez.

Hakkında `CDialog`daha fazla bilgi için bkz. [iletişim kutuları](../../mfc/dialog-boxes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

##  <a name="cdialog"></a>CDialog:: CDialog

Kaynak tabanlı kalıcı iletişim kutusu oluşturmak için, oluşturucunun ortak biçimini çağırın.

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
Bir iletişim kutusu şablon kaynağının adı olan null ile sonlandırılmış bir dize içerir.

*Nıdtemplate*<br/>
Bir iletişim kutusu şablon kaynağının KIMLIK numarasını içerir.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst veya sahip pencere nesnesine ( [CWnd](../../mfc/reference/cwnd-class.md)türü) işaret eder. NULL ise, iletişim kutusu nesnesinin ana penceresi ana uygulama penceresine ayarlanır.

### <a name="remarks"></a>Açıklamalar

Oluşturucunun bir biçimi, şablon adına göre iletişim kaynağına erişim sağlar. Diğer Oluşturucu, genellikle bir **IDD_** öneki (ÖRNEĞIN, IDD_DIALOG1) Ile şablon kimlik numarasına göre erişim sağlar.

Bellekteki bir şablondan kalıcı iletişim kutusu oluşturmak için, önce parametresiz, korumalı oluşturucuyu çağırın ve ardından öğesini çağırın `InitModalIndirect`.

Yukarıdaki yöntemlerden biriyle kalıcı iletişim kutusu oluşturduktan sonra çağrısı `DoModal`yapın.

Kalıcı olmayan bir iletişim kutusu oluşturmak için `CDialog` oluşturucunun korumalı formunu kullanın. Engelleyici bir iletişim kutusu uygulamak için kendi iletişim kutusu sınıfınızı türetmeniz gerektiğinden, Oluşturucu korunur. Kalıcı olmayan iletişim kutusunun oluşturulması iki adımlı bir işlemdir. İlk olarak oluşturucuyu çağırın; ardından, kaynak `Create` tabanlı bir iletişim kutusu oluşturmak için üye işlevini çağırın veya bellekteki bir şablondan `CreateIndirect` iletişim kutusu oluşturmak için çağrı yapın.

##  <a name="create"></a>CDialog:: Create

Bir `Create` kaynaktaki iletişim kutusu şablonunu kullanarak kalıcı olmayan iletişim kutusu oluşturma çağrısı.

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
Bir iletişim kutusu şablon kaynağının adı olan null ile sonlandırılmış bir dize içerir.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst pencere nesnesine ( [CWnd](../../mfc/reference/cwnd-class.md)türü) işaret eder. NULL ise, iletişim kutusu nesnesinin ana penceresi ana uygulama penceresine ayarlanır.

*Nıdtemplate*<br/>
Bir iletişim kutusu şablon kaynağının KIMLIK numarasını içerir.

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu oluşturma ve başlatma başarılı olduysa her iki form da sıfır dışında bir döndürür; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Çağrıyı `Create` oluşturucunun içine koyabilirsiniz veya Oluşturucu çağrıldıktan sonra bunu çağırabilirsiniz.

`Create` Üye işlevinin iki biçimi, şablon adı veya şablon kimlik numarası (örneğin, IDD_DIALOG1) tarafından iletişim kutusu şablon kaynağına erişim için sağlanır.

Her iki form için de üst pencere nesnesine bir işaretçi geçirin. *PParentWnd* null ise, iletişim kutusu üst veya sahip penceresi ana uygulama penceresine ayarlanmış olarak oluşturulur.

`Create` Üye işlevi, iletişim kutusunu oluşturduktan hemen sonra geri döndürür.

Ana pencere oluşturulduğunda iletişim kutusu görünürse, iletişim kutusu şablonundaki WS_VISIBLE stilini kullanın. Aksi takdirde, çağrısı `ShowWindow`yapmanız gerekir. Daha fazla iletişim kutusu stili ve uygulamaları için, *MFC başvurusu*içindeki Windows SDK ve [pencere stillerinde](../../mfc/reference/styles-used-by-mfc.md#window-styles) [dltemplate](/windows/win32/api/winuser/ns-winuser-dlgtemplate) yapısına bakın.

İşlev tarafından oluşturulan bir iletişim kutusunu yok etmek için işlevinikullanın.`CWnd::DestroyWindow` `Create`

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#62](../../mfc/codesnippet/cpp/cdialog-class_1.cpp)]

##  <a name="createindirect"></a>CDialog:: Createdolaylı

Bellekteki iletişim kutusu şablonundan kalıcı olmayan bir iletişim kutusu oluşturmak için bu üye işlevi çağırın.

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
İletişim kutusunu oluşturmak için kullanılan bir iletişim kutusu şablonu içeren belleğe işaret eder. Bu şablon, Windows SDK bölümünde açıklandığı gibi, bir [Dltemplate](/windows/win32/api/winuser/ns-winuser-dlgtemplate) yapısı ve denetim bilgileri biçiminde olur.

*pParentWnd*<br/>
İletişim nesnesi üst pencere nesnesine işaret eder ( [CWnd](../../mfc/reference/cwnd-class.md)türü). NULL ise, iletişim kutusu nesnesinin ana penceresi ana uygulama penceresine ayarlanır.

*lpDialogInit*<br/>
Bir DLGINıT kaynağını işaret eder.

*hDialogTemplate*<br/>
Bir iletişim kutusu şablonu içeren genel belleğe yönelik bir tanıtıcı içerir. Bu şablon, iletişim kutusundaki her bir `DLGTEMPLATE` denetimin yapısı ve verileri biçimindedir.

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu oluşturulup başarıyla başlatılmışsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CreateIndirect` Üye işlevi, iletişim kutusunu oluşturduktan hemen sonra geri döndürür.

Ana pencere oluşturulduğunda iletişim kutusu görünürse, iletişim kutusu şablonundaki WS_VISIBLE stilini kullanın. Aksi takdirde, görünmesini sağlamak `ShowWindow` için öğesini çağırmanız gerekir. Şablondaki diğer iletişim kutusu stillerini nasıl belirtebileceğiniz hakkında daha fazla bilgi için, Windows SDK üzerindeki [Dltemplate](/windows/win32/api/winuser/ns-winuser-dlgtemplate) yapısına bakın.

İşlev tarafından oluşturulan bir iletişim kutusunu yok etmek için işlevinikullanın.`CWnd::DestroyWindow` `CreateIndirect`

ActiveX denetimleri içeren iletişim kutuları, bir DLGINıT kaynağında sağlanmış ek bilgiler gerektirir.

##  <a name="domodal"></a>CDialog::D oModal

Kalıcı iletişim kutusunu çağırmak ve tamamlandığında iletişim kutusu sonucunu döndürmek için bu üye işlevini çağırın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusunu kapatmak için kullanılan [CDialog:: EndDialog](#enddialog) üye Işlevine geçirilen *nResult* parametresinin değerini belirten bir **int** değeri. İşlevin iletişim kutusu oluşturmayabilir veya başka bir hata oluştuysa, çıkış penceresinde [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)'dan hata bilgilerini içermesi durumunda dönüş değeri-1 ' dir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, iletişim kutusu etkinken kullanıcıyla tüm etkileşimi işler. İletişim kutusu kalıcı hale gelir; diğer bir deyişle, iletişim kutusu kapatılıncaya kadar Kullanıcı diğer pencereler ile etkileşime giremezsiniz.

Kullanıcı, Tamam veya Iptal gibi iletişim kutusundaki pushbutton ' ı tıklarsa, iletişim kutusunu kapatmayı denemek için [OnOK](#onok) veya [OnCancel](#oncancel)gibi bir ileti işleyici üye işlevi çağırılır. Varsayılan `OnOK` üye işlevi iletişim kutusu verisini doğrular ve güncelleştirir ve iletişim kutusunu Result IDOK ile kapatır ve varsayılan `OnCancel` üye işlevi, bu iletişim kutusunu, iletişim kutusu verileri. Davranışlarını değiştirmek için bu ileti işleyici işlevlerini geçersiz kılabilirsiniz.

> [!NOTE]
> `PreTranslateMessage`artık kalıcı iletişim kutusu ileti işleme için çağırılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#63](../../mfc/codesnippet/cpp/cdialog-class_2.cpp)]

##  <a name="enddialog"></a>CDialog:: EndDialog

Kalıcı iletişim kutusunu sonlandırmak için bu üye işlevini çağırın.

```
void EndDialog(int nResult);
```

### <a name="parameters"></a>Parametreler

*nSonuç*<br/>
İletişim kutusundan çağırana `DoModal`döndürülecek değeri içerir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, dönüş değeri `DoModal`olarak *nResult* döndürür. Kalıcı bir iletişim kutusu `EndDialog` oluşturulduğunda işlemeyi tamamlayabilmeniz için işlevini kullanmanız gerekir.

`EndDialog` [OnInitDialog](#oninitdialog)içinde bile dilediğiniz zaman çağırabilirsiniz. Bu durumda, iletişim kutusunu gösterilmeden önce veya giriş odağı ayarlamadan önce kapatmanız gerekir.

`EndDialog`iletişim kutusunu hemen kapatmaz. Bunun yerine, geçerli ileti işleyici döndüğünde iletişim kutusunu kapatmak üzere yönlendiren bir bayrak ayarlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#64](../../mfc/codesnippet/cpp/cdialog-class_3.cpp)]

[!code-cpp[NVC_MFCControlLadenDialog#65](../../mfc/codesnippet/cpp/cdialog-class_4.cpp)]

##  <a name="getdefid"></a>CDialog:: Getdeıd

Bir iletişim kutusu için varsayılan basma düğmesi denetiminin kimliğini almak için üyeişleviniçağırın.`GetDefID`

```
DWORD GetDefID() const;
```

### <a name="return-value"></a>Dönüş Değeri

32 bitlik bir değer ( `DWORD`). Varsayılan basma düğmesi bir KIMLIK değerine sahipse, yüksek sıralı sözcük DC_HASDEFID içerir ve alt sıra sözcüğü KIMLIK değerini içerir. Varsayılan basma düğmesi bir KIMLIK değerine sahip değilse, dönüş değeri 0 ' dır.

### <a name="remarks"></a>Açıklamalar

Bu genellikle bir Tamam düğmesidir.

##  <a name="gotodlgctrl"></a>CDialog:: Sayfaydlctrl

Odağı iletişim kutusunda belirtilen denetime kaydırır.

```
void GotoDlgCtrl(CWnd* pWndCtrl);
```

### <a name="parameters"></a>Parametreler

*pWndCtrl*<br/>
Odağı alacak olan pencereyi (denetim) tanımlar.

### <a name="remarks"></a>Açıklamalar

*PWndCtrl*olarak geçirilecek denetime (alt pencere) yönelik bir işaretçi almak için, [CWnd](../../mfc/reference/cwnd-class.md) nesnesine `CWnd::GetDlgItem` bir işaretçi döndüren üye işlevini çağırın.

### <a name="example"></a>Örnek

  [CWnd:: Getdlyıtem](../../mfc/reference/cwnd-class.md#getdlgitem)örneğine bakın.

##  <a name="initmodalindirect"></a>CDialog:: InitModalIndirect

Bellekte oluşturduğunuz bir iletişim kutusu şablonunu kullanarak kalıcı iletişim kutusu nesnesini başlatmak için bu üye işlevini çağırın.

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
İletişim kutusunu oluşturmak için kullanılan bir iletişim kutusu şablonu içeren belleğe işaret eder. Bu şablon, Windows SDK bölümünde açıklandığı gibi, bir [Dltemplate](/windows/win32/api/winuser/ns-winuser-dlgtemplate) yapısı ve denetim bilgileri biçiminde olur.

*hDialogTemplate*<br/>
Bir iletişim kutusu şablonu içeren genel belleğe yönelik bir tanıtıcı içerir. Bu şablon, iletişim kutusundaki her bir `DLGTEMPLATE` denetimin yapısı ve verileri biçimindedir.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst veya sahip pencere nesnesine ( [CWnd](../../mfc/reference/cwnd-class.md)türü) işaret eder. NULL ise, iletişim kutusu nesnesinin ana penceresi ana uygulama penceresine ayarlanır.

*lpDialogInit*<br/>
Bir DLGINıT kaynağını işaret eder.

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu nesnesi oluşturulup başarıyla başlatılmışsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kalıcı bir iletişim kutusunu dolaylı olarak oluşturmak için, önce genel bir bellek bloğu ayırın ve iletişim kutusu şablonuyla bu şablonu doldurmanız gerekir. Ardından, iletişim kutusu `CDialog` nesnesini oluşturmak için boş oluşturucuyu çağırın. Daha sonra, `InitModalIndirect` tanıtıcıyı bellek içi iletişim kutusu şablonuna depolamak için öğesini çağırın. Windows iletişim kutusu oluşturulur ve daha sonra [Dokalıcı](#domodal) üye işlevi çağrıldığında görüntülenir.

ActiveX denetimleri içeren iletişim kutuları, bir DLGINıT kaynağında sağlanmış ek bilgiler gerektirir.

##  <a name="mapdialogrect"></a>CDialog:: MapDialogRect

Dikdörtgenin iletişim kutusu birimlerini ekran birimlerine dönüştürmek için çağırın.

```
void MapDialogRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
Dönüştürülecek iletişim kutusu koordinatlarını içeren bir [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına veya [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine işaret eder.

### <a name="remarks"></a>Açıklamalar

İletişim kutusu birimleri, iletişim kutusu metni için kullanılan yazı tipindeki ortalama genişlik ve karakterlerin yüksekliğinden türetilmiş geçerli iletişim kutusu taban birimi açısından belirtilir. Bir yatay birim iletişim kutusu taban genişliği biriminin dörtte biridir ve bir dikey birim iletişim kutusu Taban yükseklik biriminin sekizde biridir.

`GetDialogBaseUnits` Windows işlevi, sistem yazı tipi için boyut bilgilerini döndürür, ancak kaynak tanımı dosyasında DS_SETFONT stilini kullanırsanız her iletişim kutusu için farklı bir yazı tipi belirtebilirsiniz. `MapDialogRect` Windows işlevi bu iletişim kutusu için uygun yazı tipini kullanır.

Üye işlevi, *loprect* 'daki iletişim kutusu birimlerinin yerini ekran birimleri (piksel) ile değiştirir, böylece dikdörtgen bir iletişim kutusu oluşturmak veya bir kutuyu kutu içinde konumlandırmak için kullanılabilir. `MapDialogRect`

##  <a name="nextdlgctrl"></a>CDialog:: Nextdlctrl

Odağı iletişim kutusunda bir sonraki denetime kaydırır.

```
void NextDlgCtrl() const;
```

### <a name="remarks"></a>Açıklamalar

Odak iletişim kutusundaki son denetimdir, ilk denetime taşınır.

##  <a name="oncancel"></a>CDialog:: OnCancel

Kullanıcı **iptal** ' i tıklattığında veya kalıcı veya kalıcı olmayan ILETIŞIM kutusunda ESC tuşuna basarsa Framework bu yöntemi çağırır.

```
virtual void OnCancel();
```

### <a name="remarks"></a>Açıklamalar

Bir Kullanıcı, iletişim kutusunu **Iptal et** veya ESC tuşuna basarak bir Kullanıcı iletişim kutusu kapattığında, eylemler gerçekleştirmek için bu yöntemi geçersiz kılın (eski verileri geri yükleme gibi). Varsayılan olarak, [EndDialog](#enddialog) çağırarak kalıcı iletişim kutusu kapanır ve [DOMODAL](#domodal) , IDCANCEL döndürecek şekilde olur.

Kalıcı olmayan bir iletişim kutusunda **iptal** düğmesini uygularsanız, `OnCancel` yöntemini geçersiz kılmanız ve içindeki [destroonwindow](../../mfc/reference/cwnd-class.md#destroywindow) 'u çağırmanız gerekir. , İletişim kutusunun görünmez olmasına rağmen yok etmez, çağrı `EndDialog`yaptığı için temel sınıf yöntemini çağırmayın.

> [!NOTE]
>  Windows XP altında derlenmiş bir programda bir `CFileDialog` nesne kullandığınızda bu yöntemi geçersiz kılamazsınız. Hakkında `CFileDialog`daha fazla bilgi için bkz. [CFileDialog Class](../../mfc/reference/cfiledialog-class.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#66](../../mfc/codesnippet/cpp/cdialog-class_5.cpp)]

##  <a name="oninitdialog"></a>CDialog:: OnInitDialog

Bu yöntem `WM_INITDIALOG` iletiye yanıt olarak çağırılır.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın giriş odağını iletişim kutusundaki denetimlerden birine ayarlayıp ayarlamadığını belirtir. Sıfır dışında bir değer döndürürse, Windows giriş odağını, iletişim kutusundaki ilk denetim olan varsayılan konuma ayarlar. `OnInitDialog` Uygulama, yalnızca giriş odağını iletişim kutusundaki denetimlerden birine açıkça ayarlamışsa 0 döndürebilir.

### <a name="remarks"></a>Açıklamalar

Windows, iletişim `WM_INITDIALOG` kutusu görüntülenmeden hemen önce gerçekleşen [Create](#create), [createdolaylı](#createindirect)veya [DoModal](#domodal) çağrıları sırasında iletiyi iletişim kutusuna gönderir.

İletişim kutusu başlatıldığında özel işlem gerçekleştirmek istiyorsanız bu yöntemi geçersiz kılın. Geçersiz kılınan sürümde, önce temel sınıfı `OnInitDialog` çağırın, ancak dönüş değerini yoksayın. Genellikle geçersiz kılınan yöntemden `TRUE` geri dönecektir.

Windows, `OnInitDialog` tüm Microsoft Foundation Class Kitaplığı iletişim kutularında ortak olan standart genel iletişim kutusu yordamını kullanarak işlevi çağırır. İleti haritanız aracılığıyla bu işlevi çağırmaz ve bu nedenle bu yöntem için bir ileti eşleme girişi gerekmez.

> [!NOTE]
> Windows Vista veya sonraki işletim sistemleri altında derlenmiş bir `CFileDialog` programda bir nesne kullandığınızda bu yöntemi geçersiz kılamazsınız. Windows Vista ve sonraki sürümlerinde yapılan `CFileDialog` değişiklikler hakkında daha fazla bilgi için bkz. [CFileDialog Class](../../mfc/reference/cfiledialog-class.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#67](../../mfc/codesnippet/cpp/cdialog-class_6.cpp)]

##  <a name="onok"></a>CDialog:: OnOK

Kullanıcı **Tamam** düğmesine tıkladığında çağırılır (bir kimliği IDOK olan düğme).

```
virtual void OnOK();
```

### <a name="remarks"></a>Açıklamalar

**Tamam** düğmesi etkinleştirildiğinde eylemleri gerçekleştirmek için bu yöntemi geçersiz kılın. İletişim kutusu otomatik veri doğrulama ve değişim içeriyorsa, bu yöntemin varsayılan uygulaması iletişim kutusu verilerini doğrular ve uygulamanızda uygun değişkenleri günceller.

Kalıcı olmayan bir iletişim kutusunda **Tamam** düğmesini uygularsanız, `OnOK` yöntemi geçersiz kılmalı ve içinde [destroonwindow](../../mfc/reference/cwnd-class.md#destroywindow) çağrısı yapmanız gerekir. İletişim kutusunu görünmez ancak yok etmez, [EndDialog](#enddialog) 'u çağırdığı için taban sınıfı yöntemini çağırmayın.

> [!NOTE]
>  Windows XP altında derlenmiş bir programda bir `CFileDialog` nesne kullandığınızda bu yöntemi geçersiz kılamazsınız. Hakkında `CFileDialog`daha fazla bilgi için bkz. [CFileDialog Class](../../mfc/reference/cfiledialog-class.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#68](../../mfc/codesnippet/cpp/cdialog-class_7.cpp)]

##  <a name="onsetfont"></a>CDialog:: OnSetFont

Metin çizerken bir iletişim kutusu denetiminin kullanacağı yazı tipini belirtir.

```
Virtual void OnSetFont(CFont* pFont);
```

### <a name="parameters"></a>Parametreler

*pFont*<br/>
'ndaki Bu iletişim kutusundaki tüm denetimler için varsayılan yazı tipi olarak kullanılacak yazı tipine yönelik bir işaretçi belirtir.

### <a name="remarks"></a>Açıklamalar

İletişim kutusu, tüm denetimleri için varsayılan olarak belirtilen yazı tipini kullanacaktır.

İletişim kutusu Düzenleyicisi, genellikle iletişim kutusu şablon kaynağının bir parçası olarak iletişim kutusu yazı tipini ayarlar.

> [!NOTE]
> Windows Vista veya sonraki işletim sistemleri altında derlenmiş bir `CFileDialog` programda bir nesne kullandığınızda bu yöntemi geçersiz kılamazsınız. Windows Vista ve sonraki sürümlerinde yapılan `CFileDialog` değişiklikler hakkında daha fazla bilgi için bkz. [CFileDialog Class](../../mfc/reference/cfiledialog-class.md).

##  <a name="prevdlgctrl"></a>CDialog::P revDlgCtrl

Odağı iletişim kutusunda bir önceki denetime ayarlar.

```
void PrevDlgCtrl() const;
```

### <a name="remarks"></a>Açıklamalar

Odak, iletişim kutusundaki ilk denetdeyse, kutudaki son denetime taşınır.

##  <a name="setdefid"></a>CDialog:: Setdeıd

Bir iletişim kutusu için varsayılan basma düğmesi denetimini değiştirir.

```
void SetDefID(UINT nID);
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
Varsayılan değer olacak basma düğmesi denetiminin KIMLIĞINI belirtir.

##  <a name="sethelpid"></a>CDialog:: SetHelpID

İletişim kutusu için bağlama duyarlı bir yardım KIMLIĞI ayarlar.

```
void SetHelpID(UINT nIDR);
```

### <a name="parameters"></a>Parametreler

*Nıdr*<br/>
Bağlama duyarlı yardım KIMLIĞINI belirtir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek DLGCBR32](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek bir DLTEMPL](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
