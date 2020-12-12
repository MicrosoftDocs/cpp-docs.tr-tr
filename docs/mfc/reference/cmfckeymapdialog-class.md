---
description: 'Daha fazla bilgi edinin: CMFCKeyMapDialog sınıfı'
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
ms.openlocfilehash: e339edb54b9c381dd2b27c9ee3ec7566308ae434
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265239"
---
# <a name="cmfckeymapdialog-class"></a>CMFCKeyMapDialog sınıfı

`CMFCKeyMapDialog`Sınıfı, komutları klavyedeki anahtarlarla eşleyen bir denetimi destekler.

## <a name="syntax"></a>Syntax

```
class CMFCKeyMapDialog : public CDialogEx
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCKeyMapDialog:: CMFCKeyMapDialog](#cmfckeymapdialog)|Bir `CMFCKeyMapDialog` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCKeyMapDialog::D oModal](#domodal)|Klavye eşleme iletişim kutusunu görüntüler.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCKeyMapDialog:: Formatıtem](#formatitem)|Anahtar eşlemesini açıklayan bir dize oluşturmak için Framework tarafından çağırılır. Varsayılan olarak dize, komut adını, kullanılan kısayol tuşlarını ve kısayol tuşu açıklamasını içerir.|
|[CMFCKeyMapDialog:: GetCommandKeys](#getcommandkeys)|Belirtilen komutla ilişkili kısayol tuşlarının listesini içeren bir dize alır.|
|[CMFCKeyMapDialog:: Onınsertıtem](#oninsertitem)|Klavye eşleme denetimini destekleyen iç liste denetimine yeni bir öğe eklenmeden önce Framework tarafından çağırılır.|
|[CMFCKeyMapDialog:: OnPrintHeader](#onprintheader)|Klavye haritasının başlığını yeni bir sayfada yazdırmak için Framework tarafından çağırılır.|
|[CMFCKeyMapDialog:: OnPrintItem](#onprintitem)|Bir klavye eşleme öğesini yazdırmak için Framework tarafından çağırılır.|
|[CMFCKeyMapDialog:: OnSetColumns](#onsetcolumns)|Klavye eşleme denetimini destekleyen iç liste denetimindeki sütunlar için açıklamalı alt yazılar ayarlamak üzere Framework tarafından çağırılır.|
|[CMFCKeyMapDialog::P rintKeyMap](#printkeymap)|Kullanıcı **Yazdır** düğmesine tıkladığında Framework tarafından çağırılır.|
|[CMFCKeyMapDialog:: Setcolumnyüzdth](#setcolumnswidth)|Klavye eşleme denetimini destekleyen iç liste denetimindeki sütunların genişliğini ayarlamak için Framework tarafından çağırılır.|

## <a name="remarks"></a>Açıklamalar

Yeniden `CMFCKeyMapDialog` boyutlandırılabilir bir klavye eşleme iletişim kutusu uygulamak için sınıfını kullanın. İletişim kutusu, klavye kısayollarını ve bunlarla ilişkili komutları görüntülemek için bir liste görünümü denetimi kullanır.

`CMFCKeyMapDialog`Bir uygulamadaki sınıfını kullanmak için, ana çerçeve penceresine, oluşturucuya bir parametre olarak bir işaretçi geçirin `CMFCKeyMapDialog` . Ardından, `DoModal` bir kalıcı iletişim kutusu başlatmak için yöntemini çağırın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCKeyMapDialog](../../mfc/reference/cmfckeymapdialog-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxkeymapdialog. h

## <a name="cmfckeymapdialogcmfckeymapdialog"></a><a name="cmfckeymapdialog"></a> CMFCKeyMapDialog:: CMFCKeyMapDialog

Bir `CMFCKeyMapDialog` nesnesi oluşturur.

```
CMFCKeyMapDialog(
    CFrameWnd* pWndParentFrame,
    BOOL bEnablePrint=FALSE);
```

### <a name="parameters"></a>Parametreler

*pWndParentFrame*<br/>
'ndaki Nesnenin üst penceresine yönelik bir işaretçi `CMFCKeyMapDialog` .

*bEnablePrint*<br/>
'ndaki Hızlandırıcı anahtarlarının listesi yazdırılabiliyorsa TRUE; Aksi takdirde, FALSE. Varsayılan değer FALSE 'dur.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının bir nesnesinin nasıl oluşturulduğunu gösterir `CMFCKeyMapDialog` . Bu örnek, [Visual Studio Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_VisualStudioDemo#21](../../mfc/codesnippet/cpp/cmfckeymapdialog-class_1.cpp)]

## <a name="cmfckeymapdialogdomodal"></a><a name="domodal"></a> CMFCKeyMapDialog::D oModal

Klavye eşleme iletişim kutusunu görüntüler.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Dönüş Değeri

[CDialog:: EndDialog](../../mfc/reference/cdialog-class.md#enddialog) yöntemine geçirilen IDOK veya IDCANCEL gibi işaretli bir tamsayı. Yöntemi, sırasıyla iletişim kutusunu kapatır. Daha fazla bilgi için bkz. [CDialog::D oModal](../../mfc/reference/cdialog-class.md#domodal).

### <a name="remarks"></a>Açıklamalar

Klavye eşleme iletişim kutusu, kısayol tuşlarını seçmenizi ve çeşitli komut kategorilerine atamanızı sağlar. Ayrıca, seçili Hızlandırıcı anahtarlarını ve bunların açıklamalarını panoya kopyalayabilirsiniz.

## <a name="cmfckeymapdialogformatitem"></a><a name="formatitem"></a> CMFCKeyMapDialog:: Formatıtem

Anahtar eşlemesini açıklayan bir dize oluşturmak için Framework tarafından çağırılır. Varsayılan olarak dize, komut adını, kullanılan kısayol tuşlarını ve kısayol tuşu açıklamasını içerir.

```
virtual CString FormatItem(int nItem) const;
```

### <a name="parameters"></a>Parametreler

*nÖğe*<br/>
'ndaki Anahtar eşlemelerinin iç listesindeki bir öğenin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

`CString`Biçimlendirilen öğe metnini içeren nesne.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfckeymapdialoggetcommandkeys"></a><a name="getcommandkeys"></a> CMFCKeyMapDialog:: GetCommandKeys

Bir dize değeri alır. Dize, belirtilen komutla ilişkili kısayol tuşlarının bir listesini içerir.

```
virtual CString GetCommandKeys(UINT uiCmdID) const;
```

### <a name="parameters"></a>Parametreler

*Uıımıdıd*<br/>
'ndaki Bir komut KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen komutla ilişkilendirilmiş kısayol tuşlarının bir noktalı virgülle ayrılmış ('; ') listesi.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfckeymapdialogoninsertitem"></a><a name="oninsertitem"></a> CMFCKeyMapDialog:: Onınsertıtem

Klavye eşleme denetimini destekleyen iç liste denetimine yeni bir öğe eklenmeden önce Framework tarafından çağırılır.

```
virtual void OnInsertItem(
    CMFCToolBarButton* pButton,
    int nItem);
```

### <a name="parameters"></a>Parametreler

*pButton*<br/>
'ndaki Bir klavye tuş birleşimini komut adı ve açıklama ile eşlemek için kullanılan bir araç çubuğu düğmesine yönelik bir işaretçi. Anahtar eşleme öğesi bir iç liste denetiminde depolanır.

*nÖğe*<br/>
'ndaki İç liste denetiminde yeni anahtar eşleme öğesinin nereye ekleneceği belirten sıfır tabanlı bir dizin.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfckeymapdialogonprintheader"></a><a name="onprintheader"></a> CMFCKeyMapDialog:: OnPrintHeader

Klavye haritasının başlığını yeni bir sayfada yazdırmak için Framework tarafından çağırılır.

```
virtual int OnPrintHeader(
    CDC& dc,
    int nPage,
    int cx) const;
```

### <a name="parameters"></a>Parametreler

*'ye*<br/>
'ndaki Yazıcının cihaz bağlamı.

*Nsayfa*<br/>
'ndaki Yazdırılacak sayfa numarası.

*yazmaç*<br/>
'ndaki Üstbilginin piksel cinsinden yatay boşluğu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, yazdırılan metnin yüksekliği. Daha fazla bilgi için, [CDC::D rawText](../../mfc/reference/cdc-class.md#drawtext)öğesinin dönüş değeri bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Framework, klavye eşlemesini yazdırmak için bu yöntemi kullanır. Varsayılan olarak, bu yöntem sayfa numarasını, uygulama adını ve iletişim kutusu başlığını yazdırır.

## <a name="cmfckeymapdialogonprintitem"></a><a name="onprintitem"></a> CMFCKeyMapDialog:: OnPrintItem

Bir klavye eşleme öğesini yazdırmak için Framework tarafından çağırılır.

```
virtual int OnPrintItem(
    CDC& dc,
    int nItem,
    int y,
    int cx,
    BOOL bCalcHeight) const;
```

### <a name="parameters"></a>Parametreler

*'ye*<br/>
'ndaki Yazıcının cihaz bağlamı.

*nÖğe*<br/>
'ndaki Yazdırılacak öğenin sıfır tabanlı dizini.

*Iz*<br/>
'ndaki Sayfanın üst ve öğenin konumu arasındaki dikey fark.

*yazmaç*<br/>
'ndaki Sayfanın sol ve öğenin konumu arasındaki yatay fark.

*Bcalchsekiz*<br/>
'ndaki Yazdırma öğesi için en iyi yüksekliği hesaplamak üzere doğru; Yazdırma öğesini varsayılan alana sığacak şekilde kesmek için FALSE.

### <a name="return-value"></a>Dönüş Değeri

Yazdırılan öğenin yüksekliği.

### <a name="remarks"></a>Açıklamalar

Çerçeve, bir anahtar eşleme iletişim kutusu öğesi yazdırmak için bu yöntemi çağırır. Varsayılan olarak, bu yöntem öğenin komut adını, kısayol tuşlarını ve komut açıklamasını yazdırır.

## <a name="cmfckeymapdialogonsetcolumns"></a><a name="onsetcolumns"></a> CMFCKeyMapDialog:: OnSetColumns

Klavye eşleme denetimini destekleyen iç liste denetimindeki sütunlar için açıklamalı alt yazılar ayarlamak üzere Framework tarafından çağırılır.

```
virtual void OnSetColumns();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem üç kaynaktan sütunların başlıklarını alır. Komut sütunu başlığı IDS_AFXBARRES_COMMAND, anahtar sütun başlığı IDS_AFXBARRES_KEYS ve Açıklama sütun başlığı IDS_AFXBARRES_DESCRIPTION ' den.

## <a name="cmfckeymapdialogprintkeymap"></a><a name="printkeymap"></a> CMFCKeyMapDialog::P rintKeyMap

Kullanıcı **Yazdır** düğmesine tıkladığında Framework tarafından çağırılır.

```
virtual void PrintKeyMap();
```

### <a name="remarks"></a>Açıklamalar

`PrintKeyMap`Yöntemi, anahtar eşlemesini yazdırır. Yeni bir yazdırma işi başlatır ve ardından tüm anahtar eşlemeleri yazdırılana kadar [CMFCKeyMapDialog:: OnPrintHeader](#onprintheader) ve [CMFCKeyMapDialog:: OnPrintItem](#onprintitem) yöntemlerini tekrar tekrar çağırır.

## <a name="cmfckeymapdialogsetcolumnswidth"></a><a name="setcolumnswidth"></a> CMFCKeyMapDialog:: Setcolumnyüzdth

Klavye eşleme denetimini destekleyen iç liste denetimindeki sütunların genişliğini ayarlamak için Framework tarafından çağırılır.

```
virtual void SetColumnsWidth();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iç liste denetiminin sütunlarını varsayılan genişlikler olarak ayarlar. İlk olarak, kısayol tuşları sütununun genişliği hesaplanır. Ardından, kalan genişliğin üçte biri komut sütununa ayrılır ve kalan iki ikisi de Açıklama sütununa ayrılır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CKeyboardManager sınıfı](../../mfc/reference/ckeyboardmanager-class.md)
