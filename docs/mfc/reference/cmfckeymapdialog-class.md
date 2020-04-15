---
title: CMFCKeyMapDialog Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::DoModal
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::FormatItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::GetCommandKeys
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnInsertItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnPrintHeader
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnPrintItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnSetColumns
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::PrintKeyMap
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::SetColumnsWidth
helpviewer_keywords:
- CMFCKeyMapDialog [MFC], CMFCKeyMapDialog
- CMFCKeyMapDialog [MFC], DoModal
- CMFCKeyMapDialog [MFC], FormatItem
- CMFCKeyMapDialog [MFC], GetCommandKeys
- CMFCKeyMapDialog [MFC], OnInsertItem
- CMFCKeyMapDialog [MFC], OnPrintHeader
- CMFCKeyMapDialog [MFC], OnPrintItem
- CMFCKeyMapDialog [MFC], OnSetColumns
- CMFCKeyMapDialog [MFC], PrintKeyMap
- CMFCKeyMapDialog [MFC], SetColumnsWidth
ms.assetid: 5feb4942-d636-462d-a162-0104dd320f4e
ms.openlocfilehash: 22aa006ce214ca720192bb761e2ff2b35a64fce3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374408"
---
# <a name="cmfckeymapdialog-class"></a>CMFCKeyMapDialog Sınıfı

Sınıf, `CMFCKeyMapDialog` klavyedeki tuşlarla komutları eşleyen bir denetimi destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCKeyMapDialog : public CDialogEx
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCKeyMapDialog::CMFCKeyMapDialog](#cmfckeymapdialog)|Bir `CMFCKeyMapDialog` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCKeyMapDialog::DoModal](#domodal)|Klavye eşleme iletişim kutusunu görüntüler.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCKeyMapDialog::BiçimÖğesi](#formatitem)|Anahtar eşlemi açıklayan bir dize oluşturmak için çerçeve tarafından çağrılır. Varsayılan olarak, dize komut adını, kullanılan kısayol tuşlarını ve kısayol tuşu açıklamasını içerir.|
|[CMFCKeyMapDialog::GetCommandKeys](#getcommandkeys)|Belirtilen komutla ilişkili kısayol anahtarlarının listesini içeren bir dize alır.|
|[CMFCKeyMapDialog::OnInsertItem](#oninsertitem)|Klavye eşleme denetimini destekleyen iç liste denetimine yeni bir öğe eklenmeden önce çerçeve tarafından çağrılır.|
|[CMFCKeyMapDialog::OnPrintHeader](#onprintheader)|Klavye haritasıüstbilgisini yeni bir sayfaya yazdırmak için çerçeve tarafından çağrılır.|
|[CMFCKeyMapDialog::OnPrintItem](#onprintitem)|Bir klavye eşleme öğesi yazdırmak için çerçeve tarafından çağrılır.|
|[CMFCKeyMapDialog::OnSetColumns](#onsetcolumns)|Klavye eşleme denetimini destekleyen iç liste denetimindeki sütunlar için altyazılar ayarlamak için çerçeve tarafından çağrılır.|
|[CMFCKeyMapDialog::PrintKeyMap](#printkeymap)|Kullanıcı **Yazdır** düğmesini tıklattığında çerçeve tarafından çağrılır.|
|[CMFCKeyMapDialog::SetColumnsWidth](#setcolumnswidth)|Klavye eşleme denetimini destekleyen iç liste denetimindeki sütunların genişliğini ayarlamak için çerçeve tarafından çağrılır.|

## <a name="remarks"></a>Açıklamalar

Yeniden `CMFCKeyMapDialog` boyutlandırılabilir klavye eşleme iletişim kutusunu uygulamak için sınıfı kullanın. İletişim kutusu, klavye kısayollarını ve ilişkili komutlarını görüntülemek için bir liste görünümü denetimi kullanır.

`CMFCKeyMapDialog` Bir uygulamada sınıfı kullanmak için, oluşturucuya parametre olarak ana çerçeve `CMFCKeyMapDialog` penceresine işaretçi geçirin. Ardından modal iletişim kutusunu başlatmak için `DoModal` yöntemi arayın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[Cmfckeymapdialog](../../mfc/reference/cmfckeymapdialog-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxkeymapdialog.h

## <a name="cmfckeymapdialogcmfckeymapdialog"></a><a name="cmfckeymapdialog"></a>CMFCKeyMapDialog::CMFCKeyMapDialog

Bir `CMFCKeyMapDialog` nesne inşa eder.

```
CMFCKeyMapDialog(
    CFrameWnd* pWndParentFrame,
    BOOL bEnablePrint=FALSE);
```

### <a name="parameters"></a>Parametreler

*pWndParentFrame*<br/>
[içinde] `CMFCKeyMapDialog` Nesnenin ana penceresine bir işaretçi.

*bEnablePrint*<br/>
[içinde] Hızlandırıcı tuşlarının listesi yazdırılabiliyorsa DOĞRU; aksi takdirde, YANLIŞ. Varsayılan FALSE'dır.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın bir nesnesinin `CMFCKeyMapDialog` nasıl inşa edilebildiğini gösterir. Bu örnek Visual [Studio Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_VisualStudioDemo#21](../../mfc/codesnippet/cpp/cmfckeymapdialog-class_1.cpp)]

## <a name="cmfckeymapdialogdomodal"></a><a name="domodal"></a>CMFCKeyMapDialog::DoModal

Klavye eşleme iletişim kutusunu görüntüler.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

IDOK veya IDCANCEL gibi, [CDialog::EndDialog](../../mfc/reference/cdialog-class.md#enddialog) yöntemine geçirilen imzalı bir tamsayı. Yöntem, sırayla, iletişim kutusunu kapatır. Daha fazla bilgi [için, CDialog bakınız::DoModal](../../mfc/reference/cdialog-class.md#domodal).

### <a name="remarks"></a>Açıklamalar

Klavye eşleme iletişim kutusu, hızlandırıcı tuşlarını seçmenizi ve çeşitli komut kategorilerine atamanızı sağlar. Ayrıca, seçili hızlandırıcı tuşlarını ve bunların açıklamasını panoya kopyalayabilirsiniz.

## <a name="cmfckeymapdialogformatitem"></a><a name="formatitem"></a>CMFCKeyMapDialog::BiçimÖğesi

Anahtar eşlemi açıklayan bir dize oluşturmak için çerçeve tarafından çağrılır. Varsayılan olarak, dize komut adını, kullanılan kısayol tuşlarını ve kısayol tuşu açıklamasını içerir.

```
virtual CString FormatItem(int nItem) const;
```

### <a name="parameters"></a>Parametreler

*nÖğe*<br/>
[içinde] Anahtar eşlemeleri iç listesindebir öğenin sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Biçimlendirilmiş öğe metnini içeren bir `CString` nesne.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfckeymapdialoggetcommandkeys"></a><a name="getcommandkeys"></a>CMFCKeyMapDialog::GetCommandKeys

Bir dize değeri alır. Dize, belirtilen bir komutla ilişkili kısayol anahtarlarının listesini içerir.

```
virtual CString GetCommandKeys(UINT uiCmdID) const;
```

### <a name="parameters"></a>Parametreler

*uiCmdID*<br/>
[içinde] Bir komut kimliği.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen komutla ilişkili kısayol tuşlarının yarı sütunlu (';') listesi.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfckeymapdialogoninsertitem"></a><a name="oninsertitem"></a>CMFCKeyMapDialog::OnInsertItem

Yeni bir öğe klavye eşleme denetimini destekleyen bir iç liste denetimine eklenmeden önce çerçeve tarafından çağrılır.

```
virtual void OnInsertItem(
    CMFCToolBarButton* pButton,
    int nItem);
```

### <a name="parameters"></a>Parametreler

*pDüğme*<br/>
[içinde] Klavye tuşu birleşimini komut adı ve açıklamayla eşlemek için kullanılan araç çubuğu düğmesine işaretçi. Anahtar eşleme öğesi bir iç liste denetiminde depolanır.

*nÖğe*<br/>
[içinde] Yeni anahtar eşharita öğesinin iç liste denetimine nereye ekalınacağını belirten sıfır tabanlı dizin.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfckeymapdialogonprintheader"></a><a name="onprintheader"></a>CMFCKeyMapDialog::OnPrintHeader

Klavye haritasıüstbilgisini yeni bir sayfaya yazdırmak için çerçeve tarafından çağrılır.

```
virtual int OnPrintHeader(
    CDC& dc,
    int nPage,
    int cx) const;
```

### <a name="parameters"></a>Parametreler

*Dc*<br/>
[içinde] Yazıcı için aygıt bağlamı.

*nPage*<br/>
[içinde] Yazdırırılacak sayfa numarası.

*Cx*<br/>
[içinde] Üstbilginin piksel olarak yatay mahsup.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, yazdırılan metnin yüksekliği. Daha fazla bilgi için [CDC::DrawText'in](../../mfc/reference/cdc-class.md#drawtext)İade Değeri bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Çerçeve klavye eşlemi yazdırmak için bu yöntemi kullanır. Varsayılan olarak, bu yöntem sayfa numarasını, uygulama adını ve iletişim kutusu başlığını yazdırır.

## <a name="cmfckeymapdialogonprintitem"></a><a name="onprintitem"></a>CMFCKeyMapDialog::OnPrintItem

Bir klavye eşleme öğesi yazdırmak için çerçeve tarafından çağrılır.

```
virtual int OnPrintItem(
    CDC& dc,
    int nItem,
    int y,
    int cx,
    BOOL bCalcHeight) const;
```

### <a name="parameters"></a>Parametreler

*Dc*<br/>
[içinde] Yazıcının aygıt bağlamı.

*nÖğe*<br/>
[içinde] Yazdırırılacak öğenin sıfır tabanlı dizini.

*Y*<br/>
[içinde] Sayfanın üst kısmı ile öğenin konumu arasındaki dikey ofset.

*Cx*<br/>
[içinde] Sayfanın solundaki ile öğenin konumu arasındaki yatay ofset.

*bCalcYükseklik*<br/>
[içinde] Yazdırma öğesi için en iyi yüksekliği hesaplamak için TRUE; Varsayılan alana sığacak şekilde yazdırma öğesini parçalamak için FALSE.

### <a name="return-value"></a>Dönüş Değeri

Yazdırılan öğenin yüksekliği.

### <a name="remarks"></a>Açıklamalar

Çerçeve, anahtar eşleme kutusu öğesi yazdırmak için bu yöntemi çağırır. Varsayılan olarak, bu yöntem öğenin komut adını, kısayol anahtarlarını ve komut açıklamasını yazdırır.

## <a name="cmfckeymapdialogonsetcolumns"></a><a name="onsetcolumns"></a>CMFCKeyMapDialog::OnSetColumns

Klavye eşleme denetimini destekleyen iç liste denetimindeki sütunlar için altyazılar ayarlamak için çerçeve tarafından çağrılır.

```
virtual void OnSetColumns();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem sütunlar için altyazıları üç kaynaktan alır. Komut sütunu başlığı IDS_AFXBARRES_COMMAND, anahtar sütun başlığı IDS_AFXBARRES_KEYS ve açıklama sütunbaşlığı IDS_AFXBARRES_DESCRIPTION.

## <a name="cmfckeymapdialogprintkeymap"></a><a name="printkeymap"></a>CMFCKeyMapDialog::PrintKeyMap

Kullanıcı **Yazdır** düğmesini tıklattığında çerçeve tarafından çağrılır.

```
virtual void PrintKeyMap();
```

### <a name="remarks"></a>Açıklamalar

Yöntem `PrintKeyMap` anahtar eşlemi yazdırır. Yeni bir yazdırma işi başlatır ve sonra tekrar tekrar [CMFCKeyMapDialog çağırır::OnPrintHeader](#onprintheader) ve [CMFCKeyMapDialog::OnPrintItem](#onprintitem) yöntemleri tüm anahtar eşlemeler yazdırılır kadar.

## <a name="cmfckeymapdialogsetcolumnswidth"></a><a name="setcolumnswidth"></a>CMFCKeyMapDialog::SetColumnsWidth

Klavye eşleme denetimini destekleyen iç liste denetimindeki sütunların genişliğini ayarlamak için çerçeve tarafından çağrılır.

```
virtual void SetColumnsWidth();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iç liste denetiminin sütunlarını varsayılan genişliklere ayarlar. İlk olarak, kısayol tuşları sütununun genişliği hesaplanır. Daha sonra kalan genişliğin üçte biri komut sütununa, geri kalan üçte ikisi ise açıklama sütununa ayrılır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CKeyboardManager Sınıfı](../../mfc/reference/ckeyboardmanager-class.md)
