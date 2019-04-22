---
title: CMFCKeyMapDialog sınıfı
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
ms.openlocfilehash: 65aa5ab0f24999ee23a97f383577b69584825502
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58774795"
---
# <a name="cmfckeymapdialog-class"></a>CMFCKeyMapDialog sınıfı

`CMFCKeyMapDialog` Sınıfı komutları klavyedeki tuşlarla eşleyen bir denetimi destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCKeyMapDialog : public CDialogEx
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCKeyMapDialog::CMFCKeyMapDialog](#cmfckeymapdialog)|Oluşturur bir `CMFCKeyMapDialog` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCKeyMapDialog::DoModal](#domodal)|Klavye eşleme iletişim kutusunu görüntüler.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCKeyMapDialog::FormatItem](#formatitem)|Tuş eşlemesini tanımlayan bir dize oluşturmak için framework tarafından çağırılır. Varsayılan olarak, komut adı, kullanılan kısayol tuşları ve kısayol anahtar açıklama dizesi içerir.|
|[CMFCKeyMapDialog::GetCommandKeys](#getcommandkeys)|Belirtilen komut ile ilişkili kısayol tuşlarının bir listesini içeren bir dize alır.|
|[CMFCKeyMapDialog::OnInsertItem](#oninsertitem)|Yeni bir öğe klavye eşleme denetimi destekleyen iç liste denetimine eklenmeden önce framework tarafından çağırılır.|
|[CMFCKeyMapDialog::OnPrintHeader](#onprintheader)|Klavye eşleme için başlığı üzerinde yeni bir sayfa yazdırmak için framework tarafından çağırılır.|
|[CMFCKeyMapDialog::OnPrintItem](#onprintitem)|Klavye eşleme öğesi yazdırmak için framework tarafından çağırılır.|
|[CMFCKeyMapDialog::OnSetColumns](#onsetcolumns)|Klavye eşleme denetimi destekleyen iç liste denetiminde sütunlar için açıklamalı alt yazılar ayarlamak için framework tarafından çağırılır.|
|[CMFCKeyMapDialog::PrintKeyMap](#printkeymap)|Kullanıcı tıkladığında framework tarafından çağırılır **yazdırma** düğmesi.|
|[CMFCKeyMapDialog::SetColumnsWidth](#setcolumnswidth)|Klavye eşleme denetimi destekleyen iç liste denetiminde sütunların genişliğini ayarlamak için framework tarafından çağırılır.|

## <a name="remarks"></a>Açıklamalar

Kullanım `CMFCKeyMapDialog` yeniden boyutlandırılabilir klavye eşleme iletişim kutusunu uygulamak için sınıfı. İletişim kutusu, klavye kısayolları ve bunlarla ilişkilendirilmiş komutları görüntülemek için bir liste görünümü denetimi kullanır.

Kullanılacak `CMFCKeyMapDialog` sınıfı bir uygulamada, bir parametre olarak ana çerçeve penceresine bir işaretçi geçirmek `CMFCKeyMapDialog` Oluşturucusu. Ardından çağırın `DoModal` kalıcı bir iletişim kutusu başlatmak için yöntemi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCKeyMapDialog](../../mfc/reference/cmfckeymapdialog-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxkeymapdialog.h

##  <a name="cmfckeymapdialog"></a>  CMFCKeyMapDialog::CMFCKeyMapDialog

Oluşturur bir `CMFCKeyMapDialog` nesne.

```
CMFCKeyMapDialog(
    CFrameWnd* pWndParentFrame,
    BOOL bEnablePrint=FALSE);
```

### <a name="parameters"></a>Parametreler

*pWndParentFrame*<br/>
[in] Üst penceresine bir işaretçi `CMFCKeyMapDialog` nesne.

*bEnablePrint*<br/>
[in] Kısayol tuşları listesi yazdırılabilir TRUE; Aksi takdirde FALSE. Varsayılan değer false'tur.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCKeyMapDialog` sınıfı. Bu örneğin parçasıdır [Visual Studio gösterim örneği](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#21](../../mfc/codesnippet/cpp/cmfckeymapdialog-class_1.cpp)]

##  <a name="domodal"></a>  CMFCKeyMapDialog::DoModal

Klavye eşleme iletişim kutusunu görüntüler.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

IDOK veya geçirilir IDCANCEL, gibi imzalı bir tamsayı [CDialog::EndDialog](../../mfc/reference/cdialog-class.md#enddialog) yöntemi. Yöntemi, sırasıyla iletişim kutusu kapanır. Daha fazla bilgi için [CDialog::DoModal](../../mfc/reference/cdialog-class.md#domodal).

### <a name="remarks"></a>Açıklamalar

Klavye eşleme iletişim kutusunu seçin ve kısayol tuşları komutları için çeşitli kategorileri atamak sağlar. Ayrıca, seçili kısayol tuşları ve bunların açıklaması panoya kopyalayabilirsiniz.

##  <a name="formatitem"></a>  CMFCKeyMapDialog::FormatItem

Tuş eşlemesini tanımlayan bir dize oluşturmak için framework tarafından çağırılır. Varsayılan olarak, komut adı, kullanılan kısayol tuşları ve kısayol anahtar açıklama dizesi içerir.

```
virtual CString FormatItem(int nItem) const;
```

### <a name="parameters"></a>Parametreler

*nItem*<br/>
[in] Anahtar eşlemelerinin iç listesinde bir öğe sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

A `CString` biçimlendirilmiş öğesi metni içeren nesne.

### <a name="remarks"></a>Açıklamalar

##  <a name="getcommandkeys"></a>  CMFCKeyMapDialog::GetCommandKeys

Bir dize değeri alır. Dize, belirtilen bir komut ile ilişkili kısayol tuşlarının bir listesini içerir.

```
virtual CString GetCommandKeys(UINT uiCmdID) const;
```

### <a name="parameters"></a>Parametreler

*uiCmdID*<br/>
[in] Komut kimliği.

### <a name="return-value"></a>Dönüş Değeri

Noktalı virgül ile ayrılmış belirtilen komutu ile ilişkilendirilmiş (';') kısayol tuşları listesi.

### <a name="remarks"></a>Açıklamalar

##  <a name="oninsertitem"></a>  CMFCKeyMapDialog::OnInsertItem

Yeni bir öğe klavye eşleme denetimi destekleyen bir iç liste denetimine eklenmeden önce framework tarafından çağırılır.

```
virtual void OnInsertItem(
    CMFCToolBarButton* pButton,
    int nItem);
```

### <a name="parameters"></a>Parametreler

*pButton*<br/>
[in] Klavye tuş bileşimi bir komut ad ve açıklama eşlemek için kullanılan bir araç çubuğu düğmesi için bir işaretçi. Anahtar eşleme öğesi bir iç liste denetiminde saklanır.

*nItem*<br/>
[in] Yeni anahtar eşleme öğesi iç listesi denetimi eklemek istediğiniz yeri belirtir sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

##  <a name="onprintheader"></a>  CMFCKeyMapDialog::OnPrintHeader

Klavye eşleme için başlığı üzerinde yeni bir sayfa yazdırmak için framework tarafından çağırılır.

```
virtual int OnPrintHeader(
    CDC& dc,
    int nPage,
    int cx) const;
```

### <a name="parameters"></a>Parametreler

*DC*<br/>
[in] Yazıcı için cihaz bağlamı.

*nPage*<br/>
[in] Yazdırılacak sayfa numarası.

*cx*<br/>
[in] Üstbilginin piksel cinsinden yatay uzaklık.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, yazdırılan metin yüksekliği. Daha fazla bilgi için dönüş değeri bölümüne bakın. [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext).

### <a name="remarks"></a>Açıklamalar

Çerçeve, klavye eşleme yazdırmak için bu yöntemi kullanır. Varsayılan olarak, bu yöntem, sayfa numarası, uygulama adı ve iletişim kutusu başlığı yazdırır.

##  <a name="onprintitem"></a>  CMFCKeyMapDialog::OnPrintItem

Klavye eşleme öğesi yazdırmak için framework tarafından çağırılır.

```
virtual int OnPrintItem(
    CDC& dc,
    int nItem,
    int y,
    int cx,
    BOOL bCalcHeight) const;
```

### <a name="parameters"></a>Parametreler

*DC*<br/>
[in] Yazıcı cihaz bağlamı.

*nItem*<br/>
[in] Yazdırmak için öğenin sıfır tabanlı dizini.

*Y*<br/>
[in] Sayfanın üst öğenin konumunu arasındaki dikey uzaklık.

*cx*<br/>
[in] Sayfanın solundaki öğenin konumunu arasındaki yatay uzaklık.

*bCalcHeight*<br/>
[in] Yazıcı öğesi için en iyi yükseklik hesaplamak için TRUE; Böylece varsayılan alanı sığar yazdırma öğesi kesmek için FALSE.

### <a name="return-value"></a>Dönüş Değeri

Yazdırılan öğe yüksekliği.

### <a name="remarks"></a>Açıklamalar

Framework anahtar eşleme iletişim kutusunu öğeyi yazdırmak için bu yöntemi çağırır. Varsayılan olarak, bu yöntem, öğenin komut adı, kısayol tuşları ve komut açıklama yazdırır.

##  <a name="onsetcolumns"></a>  CMFCKeyMapDialog::OnSetColumns

Klavye eşleme denetimi destekleyen iç liste denetiminde sütunlar için açıklamalı alt yazılar ayarlamak için framework tarafından çağırılır.

```
virtual void OnSetColumns();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem, üç kaynaklardan sütun başlıklarını alır. Komut sütun başlığını IDS_AFXBARRES_COMMAND, IDS_AFXBARRES_KEYS anahtar sütunu başlıktır ve açıklama sütun başlığını IDS_AFXBARRES_DESCRIPTION.

##  <a name="printkeymap"></a>  CMFCKeyMapDialog::PrintKeyMap

Kullanıcı tıkladığında framework tarafından çağırılır **yazdırma** düğmesi.

```
virtual void PrintKeyMap();
```

### <a name="remarks"></a>Açıklamalar

`PrintKeyMap` Yöntemi anahtar eşleme yazdırır. Yeni bir yazdırma işi başlatır ve ardından tekrar tekrar çağırır [CMFCKeyMapDialog::OnPrintHeader](#onprintheader) ve [CMFCKeyMapDialog::OnPrintItem](#onprintitem) tüm anahtar eşlemelerinin yazdırılır kadar yöntemleri.

##  <a name="setcolumnswidth"></a>  CMFCKeyMapDialog::SetColumnsWidth

Klavye eşleme denetimi destekleyen iç liste denetiminde sütunların genişliğini ayarlamak için framework tarafından çağırılır.

```
virtual void SetColumnsWidth();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem iç listesi denetimin sütunlar için varsayılan genişliğini ayarlar. Kısayol tuşları sütunun genişliği ilk olarak hesaplanır. Ardından kalan genişliğini üçte komut sütuna ayrılır ve kalan üçte iki açıklama sütuna ayrılır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CKeyboardManager Sınıfı](../../mfc/reference/ckeyboardmanager-class.md)
