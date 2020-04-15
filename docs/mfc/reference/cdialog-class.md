---
title: CDialog Sınıfı
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
ms.openlocfilehash: cad762f426012d9d1931b96d54d8a53c9bab465d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375641"
---
# <a name="cdialog-class"></a>CDialog Sınıfı

İletişim kutularını ekranda görüntülemek için kullanılan taban sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CDialog : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDialog::CDialog](#cdialog)|Bir `CDialog` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDialog::Oluştur](#create)|Nesneyi baş `CDialog` harfe doğru laştırır. Modeless iletişim kutusu oluşturur ve `CDialog` nesneye bağlar.|
|[CDialog::CreateIndirect](#createindirect)|Bellekteki bir iletişim kutusu şablonundan (kaynak tabanlı değil) modeless iletişim kutusu oluşturur.|
|[CDialog::DoModal](#domodal)|Modal iletişim kutusunu çağırır ve yapıldığında döndürür.|
|[CDialog::EndDialog](#enddialog)|Modal iletişim kutusunu kapatır.|
|[CDialog::GetDefID](#getdefid)|İletişim kutusu için varsayılan düğme denetiminin kimliğini alır.|
|[CDialog::GotoDlgCtrl](#gotodlgctrl)|Odak noktasını iletişim kutusunda belirtilen bir iletişim kutusu denetimine taşır.|
|[CDialog::InitModalIndirect](#initmodalindirect)|Bellekteki bir iletişim kutusu şablonundan (kaynak tabanlı değil) modal iletişim kutusu oluşturur. Parametreler, işlev `DoModal` çağrılana kadar depolanır.|
|[CDialog::MapDialogRect](#mapdialogrect)|Dikdörtgenin iletişim kutusu birimlerini ekran birimlerine dönüştürür.|
|[CDialog::NextDlgCtrl](#nextdlgctrl)|Odağı iletişim kutusundaki bir sonraki iletişim kutusu denetimine taşır.|
|[CDialog::OnInitDialog](#oninitdialog)|İletişim kutusu başlatmayı artırmak için geçersiz kılın.|
|[CDialog::OnSetFont](#onsetfont)|Metin çizerken iletişim kutusu denetiminin kullanacağı yazı tipini belirtmek için geçersiz kılma.|
|[CDialog::PrevDlgCtrl](#prevdlgctrl)|Odak noktasını iletişim kutusundaki önceki iletişim kutusu denetimine taşır.|
|[CDialog::SetDefID](#setdefid)|Bir iletişim kutusu için varsayılan basma düğmesi denetimini belirtilen bir düğmeyle değiştirir.|
|[CDialog::SetHelpID](#sethelpid)|İletişim kutusu için içeriğe duyarlı bir yardım kimliği ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDialog::OnCancel](#oncancel)|İptal düğmesini veya ESC tuş eylemini gerçekleştirmek için geçersiz kılın. Varsayılan iletişim kutusunu kapatır ve `DoModal` IDCANCEL'ı döndürür.|
|[CDialog::OnOK](#onok)|Modal iletişim kutusunda Tamam düğmesi eylemini gerçekleştirmek için geçersiz kılın. Varsayılan iletişim kutusunu kapatır ve `DoModal` IDOK döndürür.|

## <a name="remarks"></a>Açıklamalar

İletişim kutuları iki türdedir: modal ve modeless. Uygulama devam etmeden önce bir modal iletişim kutusu kullanıcı tarafından kapatılmalıdır. Modeless iletişim kutusu, kullanıcının iletişim kutusunu görüntülemesine ve iletişim kutusunu iptal etmeden veya kaldırmadan başka bir göreve dönmesini sağlar.

Nesne, `CDialog` iletişim şablonu ve `CDialog`türetilmiş sınıfın birleşimidir. İletişim şablonu oluşturmak ve bir kaynakta depolamak için iletişim düzenleyicisini kullanın, ardından sınıf `CDialog`ekle sihirbazından türetilmiş bir sınıf oluşturmak için kullanın.

Diğer tüm pencereler gibi bir iletişim kutusu da Windows'tan ileti alır. Bir iletişim kutusunda, özellikle iletişim kutusunun denetimlerinden gelen bildirim iletilerini işlemek le ilgileniyorsunuz, çünkü kullanıcı iletişim kutunuzla bu şekilde etkileşimde bulunmaktadır. Hangi iletileri işlemek istediğinizi seçmek için [Sınıf Sihirbazı'nı](mfc-class-wizard.md) kullanın ve sizin için sınıfa uygun ileti eşlemi girişleri ve ileti işleyiciüye işlevlerini ekleyin. Yalnızca işleyici üye işlevlerinde uygulamaya özgü kod yazmanız gerekir.

İsterseniz, ileti-harita girişlerini ve üye işlevleri her zaman el ile yazabilirsiniz.

En önemsiz iletişim kutusu hariç hepsinde, iletişim kutusunun denetimlerine kullanıcı tarafından girilen verileri depolamak veya kullanıcı için verileri görüntülemek için türetilmiş iletişim sınıfınıza üye değişkenler eklersiniz. Üye değişkenler oluşturmak ve bunları denetimlerle ilişkilendirmek için Değişken Ekle sihirbazını kullanabilirsiniz. Aynı zamanda, her değişken için bir değişken türü ve izin verilen değer aralığı seçersiniz. Kod sihirbazı, türemiş iletişim sınıfınıza üye değişkenleri ekler.

Üye değişkenler ve iletişim kutusunun denetimleri arasındaki veri alışverişini otomatik olarak işlemek için bir veri eşlemi oluşturulur. Veri eşlemi, iletişim kutusundaki denetimleri uygun değerlerle açan, verileri alan ve verileri doğrulayan işlevler sağlar.

Modal iletişim kutusu oluşturmak için, türemiş iletişim sınıfınız için oluşturucuyu kullanarak `DoModal` yığında bir nesne oluşturun ve ardından iletişim penceresi ve denetimlerini oluşturmak için arayın. Modeless bir iletişim kutusu oluşturmak istiyorsanız, iletişim sınıfınızın oluşturucusunu arayın. `Create`

Windows SDK'da açıklandığı gibi [bir DLGTEMPLATE](/windows/win32/api/winuser/ns-winuser-dlgtemplate) veri yapısı kullanarak bellekte bir şablon da oluşturabilirsiniz. Bir `CDialog` nesne oluşturduktan sonra, modeless iletişim kutusu oluşturmak için [CreateIndirect'i](#createindirect) arayın veya modal iletişim kutusu oluşturmak için [InitModalIndirect](#initmodalindirect) ve [DoModal'ı](#domodal) arayın.

Değişim ve doğrulama veri eşlemi, yeni `CWnd::DoDataExchange` iletişim sınıfınıza eklenen geçersiz kılmayla yazılır. Değişim ve doğrulama işlevi `CWnd` hakkında daha fazla bilgi için [DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange) üye işlevine bakın.

Hem programcı hem de `DoDataExchange` [framework, CWnd'yi](../../mfc/reference/cwnd-class.md#updatedata)arayarak dolaylı olarak arama::UpdateData .

Kullanıcı bir `UpdateData` modal iletişim kutusunu kapatmak için Tamam düğmesini tıklattığında çerçeve çağırır. (İptal düğmesi tıklanırsa veriler alınmaz.) [OnInitDialog'un](#oninitdialog) varsayılan uygulaması `UpdateData` denetimlerin başlangıç değerlerini ayarlamak için de çağrıda bulunur. Denetimleri daha `OnInitDialog` fazla başlatmayı denetlemek için genellikle geçersiz kılarsınız. `OnInitDialog`tüm iletişim denetimleri oluşturulduktan sonra ve iletişim kutusu görüntülenmeden hemen önce çağrılır.

Modal `CWnd::UpdateData` veya modeless iletişim kutusunun yürütülmesi sırasında istediğiniz zaman arayabilirsiniz.

Elle bir iletişim kutusu geliştirirseniz, türemiş iletişim kutusu sınıfına gerekli üye değişkenleri kendiniz eklersiniz ve bu değerleri ayarlamak veya almak için üye işlevler eklersiniz.

Modal iletişim kutusu, kullanıcı Tamam veya İptal düğmelerine bastığında veya kodunuz `EndDialog` üye işlevini aradığında otomatik olarak kapanır.

Modeless iletişim kutusu uyguladığınız zaman, `OnCancel` her zaman üye `DestroyWindow` işlevi geçersiz kılın ve içinden arayın. Taban sınıf `CDialog::OnCancel`aramayın , çünkü `EndDialog`çağrı yapar , iletişim kutusunu görünmez yapacak ama yok etmez. Modsuz iletişim `PostNcDestroy` kutuları genellikle **yeni**ile tahsis olduğundan, **bu**silmek için modsuz iletişim kutuları için geçersiz kılmanız gerekir. Modal iletişim kutuları genellikle çerçeve üzerine inşa `PostNcDestroy` edilir ve temizleme gerekmez.

Daha fazla `CDialog`bilgi için Bkz. [İletişim Kutuları.](../../mfc/dialog-boxes.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cdialogcdialog"></a><a name="cdialog"></a>CDialog::CDialog

Kaynak tabanlı bir modal iletişim kutusu oluşturmak için, oluşturucunun ortak biçimini arayın.

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
İletişim kutusu şablon uytunun adı olan null-sonlandırılan bir dize içerir.

*nIDTemplate*<br/>
İletişim kutusu şablonkaynağının kimlik numarasını içerir.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst veya sahip penceresi nesnesine [(CWnd](../../mfc/reference/cwnd-class.md)türünden) işaret eder. NULL ise, iletişim nesnesinin üst penceresi ana uygulama penceresine ayarlanır.

### <a name="remarks"></a>Açıklamalar

Oluşturucubir form şablon adına göre iletişim kaynağına erişim sağlar. Diğer oluşturucu, genellikle **IDD_** bir önek (örneğin, IDD_DIALOG1) ile şablon kimlik numarasına göre erişim sağlar.

Bellekteki bir şablondan modal iletişim kutusu oluşturmak için önce parametresiz, korumalı oluşturucuyu çağırın ve ardından çağırın. `InitModalIndirect`

Yukarıdaki yöntemlerden biriyle bir modal iletişim kutusu yaptıktan `DoModal`sonra, arayın.

Modeless iletişim kutusu oluşturmak için `CDialog` oluşturucunun korumalı biçimini kullanın. Modeless iletişim kutusu uygulamak için kendi iletişim kutusu sınıftürseniz gerekir, çünkü oluşturucu korunur. Modeless iletişim kutusunun yapımı iki adımlı bir işlemdir. Önce yapıcıyı arayın; ardından `Create` kaynak tabanlı iletişim kutusu oluşturmak için üye işlevi `CreateIndirect` arayın veya bellekteki bir şablondan iletişim kutusunu oluşturmak için arayın.

## <a name="cdialogcreate"></a><a name="create"></a>CDialog::Oluştur

Kaynaktan gelen iletişim kutusu şablonunu kullanarak modeless iletişim kutusu oluşturmak için arayın. `Create`

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
İletişim kutusu şablon uytunun adı olan null-sonlandırılan bir dize içerir.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu ana pencere nesnesine [(CWnd](../../mfc/reference/cwnd-class.md)türünden) işaret eder. NULL ise, iletişim nesnesinin üst penceresi ana uygulama penceresine ayarlanır.

*nIDTemplate*<br/>
İletişim kutusu şablonkaynağının kimlik numarasını içerir.

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu oluşturma ve başlatma başarılı olursa her iki form da sıfırsız döndürülme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Çağrıyı yapıcının `Create` içine koyabilir veya oluşturucu çağrıldıktan sonra arayabilirsiniz.

`Create` Şablon adı veya şablon kimlik numarası (örneğin, IDD_DIALOG1) tarafından iletişim kutusu şablon kaynağına erişmek için üye işlevin iki biçimi sağlanır.

Her iki form için de bir işaretçiyi ana pencere nesnesine geçirin. *pParentWnd* NULL ise, iletişim kutusu ana uygulama penceresine ayarlanmış üst veya sahibi penceresi ile oluşturulur.

Üye `Create` işlev, iletişim kutusunu oluşturduktan hemen sonra geri döner.

Ana pencere oluşturulduğunda iletişim kutusu nun görünmesi gerekiyorsa, iletişim kutusu şablonundaki WS_VISIBLE stilini kullanın. Aksi takdirde, `ShowWindow`aramanız gerekir. Daha fazla iletişim kutusu stilleri ve bunların uygulamaları için, *MFC Başvurusu'ndaki*Windows SDK ve [Pencere Stilleri'ndeki](../../mfc/reference/styles-used-by-mfc.md#window-styles) [DLGTEMPLATE](/windows/win32/api/winuser/ns-winuser-dlgtemplate) yapısına bakın.

`CWnd::DestroyWindow` İşlev tarafından oluşturulan iletişim kutusunu yok etmek için işlevi `Create` kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#62](../../mfc/codesnippet/cpp/cdialog-class_1.cpp)]

## <a name="cdialogcreateindirect"></a><a name="createindirect"></a>CDialog::CreateIndirect

Bellekteki bir iletişim kutusu şablonundan modeless iletişim kutusu oluşturmak için bu üye işlevini arayın.

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
İletişim kutusunu oluşturmak için kullanılan bir iletişim kutusu şablonu içeren belleğe işaret. Bu şablon, Windows SDK'da açıklandığı gibi Bir [DLGTEMPLATE](/windows/win32/api/winuser/ns-winuser-dlgtemplate) yapısı ve denetim bilgileri şeklindedir.

*pParentWnd*<br/>
İletişim nesnesinin ana pencere nesnesine [(CWnd](../../mfc/reference/cwnd-class.md)türünden) işaret eder. NULL ise, iletişim nesnesinin üst penceresi ana uygulama penceresine ayarlanır.

*lpDialogInit*<br/>
Bir DLGINIT kaynağına işaret edin.

*hDialogTemplate*<br/>
İletişim kutusu şablonu içeren genel belleğe bir tanıtıcı içerir. Bu şablon, iletişim kutusundaki her denetim için bir `DLGTEMPLATE` yapı ve veri biçimindedir.

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu oluşturulduysa ve başarılı bir şekilde başharfe vurulduysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Üye `CreateIndirect` işlev, iletişim kutusunu oluşturduktan hemen sonra geri döner.

Ana pencere oluşturulduğunda iletişim kutusu nun görünmesi gerekiyorsa, iletişim kutusu şablonundaki WS_VISIBLE stilini kullanın. Aksi takdirde, `ShowWindow` görünmesine neden olmak için aramanız gerekir. Şablondaki diğer iletişim kutusu stillerini nasıl belirtebileceğiniz hakkında daha fazla bilgi için Windows SDK'daki [DLGTEMPLATE](/windows/win32/api/winuser/ns-winuser-dlgtemplate) yapısına bakın.

`CWnd::DestroyWindow` İşlev tarafından oluşturulan iletişim kutusunu yok etmek için işlevi `CreateIndirect` kullanın.

ActiveX denetimleri içeren iletişim kutuları, Bir DLGINIT kaynağında sağlanan ek bilgiler gerektirir.

## <a name="cdialogdomodal"></a><a name="domodal"></a>CDialog::DoModal

Modal iletişim kutusunu çağırmak ve iletişim kutusu sonucunu gerektiğinde döndürmek için bu üye işlevini arayın.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

CDialog'a geçirilen *nResult* parametresinin değerini belirten bir **int** [değeri::İletişim](#enddialog) kutusunu kapatmak için kullanılan EndDialog üye işlevi. İşlev iletişim kutusunu oluşturamazsa iade değeri -1 veya başka bir hata oluştuysa IDABORT'dur, bu durumda çıkış penceresi [GetLastError'tan](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)gelen hata bilgilerini içerir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, iletişim kutusu etkinken kullanıcıyla olan tüm etkileşimi işler. Bu iletişim kutusu modal kılan şeydir; diğer bir deyişle, iletişim kutusu kapatılana kadar kullanıcı diğer pencerelerle etkileşim kuramaz.

Kullanıcı iletişim kutusundaki Ok veya İptal gibi basma düğmelerinden birini tıklatarsa, iletişim kutusunu kapatmaya çalışmak için [OnOK](#onok) veya [OnCancel](#oncancel)gibi bir ileti işleyiciüye işlevi çağrılır. Varsayılan `OnOK` üye işlevi iletişim kutusu verilerini doğrular ve günceller ve iletişim kutusunu sonuç IDOK ile kapatır ve varsayılan `OnCancel` üye işlev iletişim kutusu verilerini doğrulamadan veya güncelleştirmeden sonuç IDCANCEL ile iletişim kutusunu kapatır. Davranışlarını değiştirmek için bu ileti işleyicisi işlevlerini geçersiz kılabilirsiniz.

> [!NOTE]
> `PreTranslateMessage`şimdi modal iletişim kutusu ileti işleme için çağrılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#63](../../mfc/codesnippet/cpp/cdialog-class_2.cpp)]

## <a name="cdialogenddialog"></a><a name="enddialog"></a>CDialog::EndDialog

Modal iletişim kutusunu sonlandırmak için bu üye işlevini arayın.

```
void EndDialog(int nResult);
```

### <a name="parameters"></a>Parametreler

*nSonuç*<br/>
İletişim kutusundan arayanın alıbına döndürülecek değeri `DoModal`içerir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev *nResult'ı* `DoModal`döndürür. Bir modal `EndDialog` iletişim kutusu oluşturulduğunda işleme tamamlamak için işlevi kullanmanız gerekir.

`EndDialog` [OnInitDialog'da](#oninitdialog)bile istediğiniz zaman arayabilirsiniz, bu durumda iletişim kutusunu gösterilmeden veya giriş odağı ayarlamadan önce kapatmanız gerekir.

`EndDialog`iletişim kutusunu hemen kapatmaz. Bunun yerine, geçerli ileti işleyicisi döndürür dönmez kapatmak için iletişim kutusunu yönlendiren bir bayrak ayarlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#64](../../mfc/codesnippet/cpp/cdialog-class_3.cpp)]

[!code-cpp[NVC_MFCControlLadenDialog#65](../../mfc/codesnippet/cpp/cdialog-class_4.cpp)]

## <a name="cdialoggetdefid"></a><a name="getdefid"></a>CDialog::GetDefID

Bir `GetDefID` iletişim kutusu için varsayılan düğme denetiminin kimliğini almak için üye işlevini arayın.

```
DWORD GetDefID() const;
```

### <a name="return-value"></a>Dönüş Değeri

32 bit lik `DWORD`bir değer ( ). Varsayılan basma düğmesinin bir kimlik değeri varsa, yüksek sıralı sözcük DC_HASDEFID içerir ve düşük sıralı sözcük kimlik değerini içerir. Varsayılan basma düğmesinin kimlik değeri yoksa, iade değeri 0'dır.

### <a name="remarks"></a>Açıklamalar

Bu genellikle tamam düğmesidir.

## <a name="cdialoggotodlgctrl"></a><a name="gotodlgctrl"></a>CDialog::GotoDlgCtrl

Odak noktasını iletişim kutusunda belirtilen denetime taşır.

```
void GotoDlgCtrl(CWnd* pWndCtrl);
```

### <a name="parameters"></a>Parametreler

*pWndCtrl*<br/>
Odağı alacak pencereyi (denetim) tanımlar.

### <a name="remarks"></a>Açıklamalar

Denetim (alt pencere) için bir işaretçi almak için *pWndCtrl*olarak geçmek için, bir `CWnd::GetDlgItem` [cWnd](../../mfc/reference/cwnd-class.md) nesnesine bir işaretçi döndürür üye işlevi arayın.

### <a name="example"></a>Örnek

  CWnd örneğine [bakın:GetDlgItem](../../mfc/reference/cwnd-class.md#getdlgitem).

## <a name="cdialoginitmodalindirect"></a><a name="initmodalindirect"></a>CDialog::InitModalIndirect

Bellekte oluşturabileceğiniz bir iletişim kutusu şablonunu kullanarak modal iletişim nesnesini başlatmak için bu üye işlevi arayın.

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
İletişim kutusunu oluşturmak için kullanılan bir iletişim kutusu şablonu içeren belleğe işaret. Bu şablon, Windows SDK'da açıklandığı gibi Bir [DLGTEMPLATE](/windows/win32/api/winuser/ns-winuser-dlgtemplate) yapısı ve denetim bilgileri şeklindedir.

*hDialogTemplate*<br/>
İletişim kutusu şablonu içeren genel belleğe bir tanıtıcı içerir. Bu şablon, iletişim kutusundaki her denetim için bir `DLGTEMPLATE` yapı ve veri biçimindedir.

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst veya sahip penceresi nesnesine [(CWnd](../../mfc/reference/cwnd-class.md)türünden) işaret eder. NULL ise, iletişim nesnesinin üst penceresi ana uygulama penceresine ayarlanır.

*lpDialogInit*<br/>
Bir DLGINIT kaynağına işaret edin.

### <a name="return-value"></a>Dönüş Değeri

İletişim nesnesi oluşturulduysa ve başarılı bir şekilde başharfe vurulduysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Modal iletişim kutusunu dolaylı olarak oluşturmak için, önce genel bir bellek bloğu ayırın ve iletişim kutusu şablonuyla doldurun. Ardından, iletişim `CDialog` kutusu nesnesini oluşturmak için boş oluşturucuyu arayın. Ardından, `InitModalIndirect` tutamacınızı bellek içi iletişim kutusu şablonuna depolamak için arayın. [DoModal](#domodal) üye işlevi çağrıldığında, Windows iletişim kutusu oluşturulur ve daha sonra görüntülenir.

ActiveX denetimleri içeren iletişim kutuları, Bir DLGINIT kaynağında sağlanan ek bilgiler gerektirir.

## <a name="cdialogmapdialogrect"></a><a name="mapdialogrect"></a>CDialog::MapDialogRect

Dikdörtgenin iletişim kutusu birimlerini ekran birimlerine dönüştürmek için arayın.

```
void MapDialogRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*Lprect*<br/>
Dönüştürülecek iletişim kutusu koordinatlarını içeren bir [RECT](/windows/win32/api/windef/ns-windef-rect) yapısına veya [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine işaret eder.

### <a name="remarks"></a>Açıklamalar

İletişim kutusu birimleri, iletişim kutusu metni için kullanılan yazı tipindeki karakterlerin ortalama genişliği ve yüksekliğinden türetilen geçerli iletişim kutusu temel birimi açısından belirtilir. Yatay birim, iletişim kutusu taban genişliği biriminin dörtte biridir ve bir dikey birim iletişim kutusu taban yüksekliği biriminin sekizde biridir.

`GetDialogBaseUnits` Windows işlevi sistem yazı tipi için boyut bilgilerini döndürür, ancak kaynak tanım dosyasındaki DS_SETFONT stilini kullanırsanız her iletişim kutusu için farklı bir yazı tipi belirtebilirsiniz. `MapDialogRect` Windows işlevi, bu iletişim kutusu için uygun yazı tipini kullanır.

Üye `MapDialogRect` işlev, kartbirimi oluşturmak veya bir kutu içinde bir denetim konumlandırmak için dikdörtgenin kullanılabilmesi için *lpRect'teki* iletişim kutusu birimlerini ekran birimleriyle (pikseller) değiştirir.

## <a name="cdialognextdlgctrl"></a><a name="nextdlgctrl"></a>CDialog::NextDlgCtrl

Odak noktasını iletişim kutusundaki bir sonraki denetime taşır.

```
void NextDlgCtrl() const;
```

### <a name="remarks"></a>Açıklamalar

Odak iletişim kutusundaki son denetimdeyse, ilk denetime geçer.

## <a name="cdialogoncancel"></a><a name="oncancel"></a>CDialog::OnCancel

Çerçeve, kullanıcı **İptal** tuşuna bastığında veya esc tuşuna modal veya modeless iletişim kutusunda bastığında bu yöntemi çağırır.

```
virtual void OnCancel();
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı, **İptal et** tuşuna basarak veya ESC tuşuna basarak iletişim kutusunu kapattığında eylemleri gerçekleştirmek için (eski verileri geri getirmek gibi) bu yöntemi geçersiz kılın. Varsayılan, [EndDialog'u](#enddialog) arayarak ve [DoModal'ın](#domodal) IDCANCEL'ı döndürmesine neden olarak bir modal iletişim kutusunu kapatır.

Modeless iletişim kutusunda **İptal** düğmesini uygularsanız, `OnCancel` yöntemi geçersiz kılmanız ve içindeki [DestroyWindow'u](../../mfc/reference/cwnd-class.md#destroywindow) aramanız gerekir. Taban sınıf yöntemini aramayın, çünkü `EndDialog`iletişim kutusunu görünmez yapacak, ancak yok etmeyecek şekilde çağırır.

> [!NOTE]
> Windows XP altında derlenen bir `CFileDialog` programda bir nesne kullandığınızda bu yöntemi geçersiz kılamazsınız. Hakkında `CFileDialog`daha fazla bilgi için [CFileDialog Class'a](../../mfc/reference/cfiledialog-class.md)bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#66](../../mfc/codesnippet/cpp/cdialog-class_5.cpp)]

## <a name="cdialogoninitdialog"></a><a name="oninitdialog"></a>CDialog::OnInitDialog

Bu yöntem `WM_INITDIALOG` iletiye yanıt olarak çağrılır.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın giriş odağı iletişim kutusundaki denetimlerden birine ayarlayıp ayarlamadığını belirtir. Sıfırsız `OnInitDialog` dönerse, Windows giriş odağı varsayılan konuma ayarlar, iletişim kutusunda ilk denetim. Uygulama, yalnızca giriş odağının iletişim kutusundaki denetimlerden birine açıkça ayarlamısa 0 döndürebilir.

### <a name="remarks"></a>Açıklamalar

Windows, `WM_INITDIALOG` iletişim kutusu görüntülenmeden hemen önce gerçekleşen [Create](#create), [CreateIndirect](#createindirect)veya [DoModal](#domodal) aramaları sırasında iletişim kutusuna iletiyi gönderir.

İletişim kutusu başharfe geçtiğinde özel işleme gerçekleştirmek istiyorsanız bu yöntemi geçersiz kılın. Geçersiz kılınan sürümde, önce taban `OnInitDialog` sınıfı arayın, ancak geri dönüş değerini yoksayın. Genellikle geçersiz kılınan yöntemden geri dönersiniz. `TRUE`

Windows, `OnInitDialog` tüm Microsoft Hazırlık Sınıfı Kitaplığı iletişim kutularında ortak olan standart genel iletişim kutusu yordamını kullanarak işlevi çağırır. Bu işlevi ileti haritanız üzerinden aramaz ve bu nedenle bu yöntem için bir ileti eşlemesi girişigerekmez.

> [!NOTE]
> Windows Vista veya daha sonraki `CFileDialog` işletim sistemleri altında derlenmiş bir programda bir nesne kullandığınızda bu yöntemi geçersiz kılamazsınız. Windows Vista `CFileDialog` altında ve daha sonra değişiklikler hakkında daha fazla bilgi için [CFileDialog Class](../../mfc/reference/cfiledialog-class.md)bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#67](../../mfc/codesnippet/cpp/cdialog-class_6.cpp)]

## <a name="cdialogonok"></a><a name="onok"></a>CDialog::OnOK

Kullanıcı **Tamam** düğmesini (IDOK kimliği içeren düğme) tıklattığında çağrılır.

```
virtual void OnOK();
```

### <a name="remarks"></a>Açıklamalar

**Tamam** düğmesi etkinleştirildiğinde eylemleri gerçekleştirmek için bu yöntemi geçersiz kılın. İletişim kutusu otomatik veri doğrulama ve alışverişi içeriyorsa, bu yöntemin varsayılan uygulaması iletişim kutusu verilerini doğrular ve uygulamanızdaki uygun değişkenleri güncelleştirir.

**Tamam** düğmesini modeless iletişim kutusunda uygularsanız, `OnOK` yöntemi geçersiz kılmanız ve içindeki [DestroyWindow'u](../../mfc/reference/cwnd-class.md#destroywindow) aramanız gerekir. Taban sınıf yöntemini aramayın, çünkü iletişim kutusunu görünmez kılan ancak onu yok etmeyen [EndDialog'u](#enddialog) çağırır.

> [!NOTE]
> Windows XP altında derlenen bir `CFileDialog` programda bir nesne kullandığınızda bu yöntemi geçersiz kılamazsınız. Hakkında `CFileDialog`daha fazla bilgi için [CFileDialog Class'a](../../mfc/reference/cfiledialog-class.md)bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCControlLadenDialog#68](../../mfc/codesnippet/cpp/cdialog-class_7.cpp)]

## <a name="cdialogonsetfont"></a><a name="onsetfont"></a>CDialog::OnSetFont

Metin çizerken iletişim kutusu denetiminin kullanacağı yazı tipini belirtir.

```
Virtual void OnSetFont(CFont* pFont);
```

### <a name="parameters"></a>Parametreler

*pFont*<br/>
[içinde] Bu iletişim kutusundaki tüm denetimler için varsayılan yazı tipi olarak kullanılacak yazı tipiiçin bir işaretçi belirtir.

### <a name="remarks"></a>Açıklamalar

İletişim kutusu, tüm denetimleri için varsayılan olarak belirtilen yazı tipini kullanır.

İletişim düzenleyicisi genellikle iletişim kutusu şablonu kaynağının bir parçası olarak iletişim kutusu yazı tipini ayarlar.

> [!NOTE]
> Windows Vista veya daha sonraki `CFileDialog` işletim sistemleri altında derlenmiş bir programda bir nesne kullandığınızda bu yöntemi geçersiz kılamazsınız. Windows Vista `CFileDialog` altında ve daha sonra değişiklikler hakkında daha fazla bilgi için [CFileDialog Class](../../mfc/reference/cfiledialog-class.md)bakın.

## <a name="cdialogprevdlgctrl"></a><a name="prevdlgctrl"></a>CDialog::PrevDlgCtrl

Odak noktasını iletişim kutusundaki önceki denetime ayarlar.

```
void PrevDlgCtrl() const;
```

### <a name="remarks"></a>Açıklamalar

Odak iletişim kutusundaki ilk denetimdeyse, kutudaki son denetime geçer.

## <a name="cdialogsetdefid"></a><a name="setdefid"></a>CDialog::SetDefID

İletişim kutusu için varsayılan düğme denetimini değiştirir.

```
void SetDefID(UINT nID);
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
Varsayılan olacak düğmeye basarak denetiminin kimliğini belirtir.

## <a name="cdialogsethelpid"></a><a name="sethelpid"></a>CDialog::SetHelpID

İletişim kutusu için içeriğe duyarlı bir yardım kimliği ayarlar.

```
void SetHelpID(UINT nIDR);
```

### <a name="parameters"></a>Parametreler

*nIDR*<br/>
İçeriğe duyarlı yardım kimliğini belirtir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek DLGCBR32](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek DLGTEMPL](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
