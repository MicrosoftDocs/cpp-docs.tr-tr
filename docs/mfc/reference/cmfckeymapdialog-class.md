---
title: CMFCKeyMapDialog sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25d86a4797479fe3ee95dde162e22cde63aaa71e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369040"
---
# <a name="cmfckeymapdialog-class"></a>CMFCKeyMapDialog sınıfı
`CMFCKeyMapDialog` Sınıfı, komutları tuşlarını eşleyen bir denetim destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCKeyMapDialog : public CDialogEx  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCKeyMapDialog::CMFCKeyMapDialog](#cmfckeymapdialog)|Oluşturan bir `CMFCKeyMapDialog` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCKeyMapDialog::DoModal](#domodal)|Klavye eşleme iletişim kutusunu görüntüler.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCKeyMapDialog::FormatItem](#formatitem)|Bir anahtar eşleme tanımlayan bir dize oluşturmak için çerçevesi tarafından çağrılır. Varsayılan olarak, komut adı, kullanılan kısayol tuşları ve kısayol anahtar açıklama dizesi içerir.|  
|[CMFCKeyMapDialog::GetCommandKeys](#getcommandkeys)|Kısayol tuşları belirtilen komutla ilişkili listesini içeren bir dize alır.|  
|[CMFCKeyMapDialog::OnInsertItem](#oninsertitem)|Yeni bir öğe klavye eşleme denetimi destekleyen iç liste denetimine eklenmeden önce çerçevesi tarafından çağrılır.|  
|[CMFCKeyMapDialog::OnPrintHeader](#onprintheader)|Üstbilgi klavye eşleme için yeni bir sayfa yazdırmak için çerçevesi tarafından çağrılır.|  
|[CMFCKeyMapDialog::OnPrintItem](#onprintitem)|Klavye eşleme öğesi yazdırmak için çerçevesi tarafından çağrılır.|  
|[CMFCKeyMapDialog::OnSetColumns](#onsetcolumns)|Klavye eşleme denetimi destekleyen iç liste denetiminde sütunlar için resim yazıları ayarlamak için çerçevesi tarafından çağrılır.|  
|[CMFCKeyMapDialog::PrintKeyMap](#printkeymap)|Bir kullanıcı tıkladığında çerçevesi tarafından çağrılır **yazdırma** düğmesi.|  
|[CMFCKeyMapDialog::SetColumnsWidth](#setcolumnswidth)|Klavye eşleme denetimi destekleyen iç liste denetiminde sütunların genişliğini ayarlamak için çerçevesi tarafından çağrılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım `CMFCKeyMapDialog` yeniden boyutlandırılabilir klavye eşleme iletişim kutusunu uygulanacak sınıf. İletişim kutusu, klavye kısayolları ve bunlarla ilişkilendirilmiş komutları görüntülemek için bir liste görünümü denetimi kullanır.  
  
 Kullanılacak `CMFCKeyMapDialog` sınıfı bir uygulamada, bir parametre olarak ana çerçeve penceresi için bir işaretçi geçirin `CMFCKeyMapDialog` Oluşturucusu. ' I çağırın `DoModal` yöntemi bir modal iletişim kutusunu başlatın.  
  
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
 Oluşturan bir `CMFCKeyMapDialog` nesnesi.  
  
```  
CMFCKeyMapDialog(
    CFrameWnd* pWndParentFrame,  
    BOOL bEnablePrint=FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pWndParentFrame`  
 Üst penceresi için bir işaretçi `CMFCKeyMapDialog` nesnesi.  
  
 [in] `bEnablePrint`  
 `TRUE` kısayol tuşları listesi yazdırılabilir; Aksi takdirde `FALSE`. Varsayılan, `FALSE` değeridir.  
  
### <a name="remarks"></a>Açıklamalar  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCKeyMapDialog` sınıfı. Bu örneğin parçasıdır [Visual Studio gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#21](../../mfc/codesnippet/cpp/cmfckeymapdialog-class_1.cpp)]  
  
##  <a name="domodal"></a>  CMFCKeyMapDialog::DoModal  
 Klavye eşleme iletişim kutusunu görüntüler.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İmzalı bir tamsayı gibi `IDOK` veya `IDCANCEL`, yani geçirilen [CDialog::EndDialog](../../mfc/reference/cdialog-class.md#enddialog) yöntemi. Yöntemi, sırasıyla iletişim kutusunu kapatır. Daha fazla bilgi için bkz: [CDialog::DoModal](../../mfc/reference/cdialog-class.md#domodal).  
  
### <a name="remarks"></a>Açıklamalar  
 Klavye eşleme iletişim kutusunu seçin ve Hızlandırıcı tuşları komutların çeşitli kategoriye atayın sağlar. Ayrıca, seçili Hızlandırıcı tuşları ve bunların açıklaması panoya kopyalayabilirsiniz.  
  
##  <a name="formatitem"></a>  CMFCKeyMapDialog::FormatItem  
 Bir anahtar eşleme tanımlayan bir dize oluşturmak için çerçevesi tarafından çağrılır. Varsayılan olarak, komut adı, kullanılan kısayol tuşları ve kısayol anahtar açıklama dizesi içerir.  
  
```  
virtual CString FormatItem(int nItem) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `nItem`  
 İç listesindeki bir öğeyi anahtar eşlemeleri sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CString` biçimlendirilmiş öğesi metni içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcommandkeys"></a>  CMFCKeyMapDialog::GetCommandKeys  
 Bir dize değerini alır. Dizeyi belirtilen komut ile ilişkili kısayol tuşları listesini içerir.  
  
```  
virtual CString GetCommandKeys(UINT uiCmdID) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `uiCmdID`  
 Komut kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Noktalı virgülle ayrılmış kısayol tuşları belirtilen komutuyla ilişkilendirilmiş (';') listesi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="oninsertitem"></a>  CMFCKeyMapDialog::OnInsertItem  
 Yeni bir öğe klavye eşleme denetimi destekleyen bir iç liste denetimine eklenmeden önce çerçevesi tarafından çağrılır.  
  
```  
virtual void OnInsertItem(
    CMFCToolBarButton* pButton,  
    int nItem);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pButton`  
 Bir komut ad ve açıklama klavye tuş bileşimini eşleştirmek için kullanılan bir araç çubuğu düğmesi için bir işaretçi. Anahtar map öğesi bir iç liste denetiminde saklanır.  
  
 [in] `nItem`  
 İç liste denetiminde yeni anahtarı eşleme öğesi eklemek istediğiniz yeri belirtir sıfır tabanlı dizini.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onprintheader"></a>  CMFCKeyMapDialog::OnPrintHeader  
 Üstbilgi klavye eşleme için yeni bir sayfa yazdırmak için çerçevesi tarafından çağrılır.  
  
```  
virtual int OnPrintHeader(
    CDC& dc,  
    int nPage,  
    int cx) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `dc`  
 Yazıcı için cihaz bağlamı.  
  
 [in] `nPage`  
 Yazdırmak için sayfa numarası.  
  
 [in] `cx`  
 Yatay uzaklığını piksel cinsinden üstbilgi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, yazdırılan metin yüksekliği. Daha fazla bilgi için dönüş değeri bölümüne bakın [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext).  
  
### <a name="remarks"></a>Açıklamalar  
 Çerçeve klavye eşleme yazdırmak için bu yöntemi kullanır. Varsayılan olarak, bu yöntem sayfa numarası, uygulama adı ve iletişim kutusu başlığı yazdırır.  
  
##  <a name="onprintitem"></a>  CMFCKeyMapDialog::OnPrintItem  
 Klavye eşleme öğesi yazdırmak için çerçevesi tarafından çağrılır.  
  
```  
virtual int OnPrintItem(
    CDC& dc,  
    int nItem,  
    int y,  
    int cx,  
    BOOL bCalcHeight) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `dc`  
 Yazıcı cihaz bağlamı.  
  
 [in] `nItem`  
 Yazdırmak için öğenin sıfır tabanlı dizini.  
  
 [in] `y`  
 Sayfanın üst öğenin konumunu arasındaki dikey uzaklık.  
  
 [in] `cx`  
 Sayfanın solunda öğenin konumunu arasındaki yatay uzaklığını.  
  
 [in] `bCalcHeight`  
 `TRUE` Yazıcı öğesi için en iyi yüksekliğini hesaplamak için; `FALSE` varsayılan alanı uyduğunu böylece yazdırma öğesi kesemez.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yazdırılan öğe yüksekliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework anahtarı eşleme iletişim kutusu öğesi yazdırmak için bu yöntemi çağırır. Varsayılan olarak, bu yöntem, öğenin komut adı, kısayol tuşları ve komut tanımı yazdırır.  
  
##  <a name="onsetcolumns"></a>  CMFCKeyMapDialog::OnSetColumns  
 Klavye eşleme denetimi destekleyen iç liste denetiminde sütunlar için resim yazıları ayarlamak için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnSetColumns();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu yöntem üç kaynaklardan sütunlar için resim yazıları alır. Komut sütun başlığını IDS_AFXBARRES_COMMAND, anahtar sütun başlığını IDS_AFXBARRES_KEYS olduğundan, ve açıklama sütun başlığını IDS_AFXBARRES_DESCRIPTION.  
  
##  <a name="printkeymap"></a>  CMFCKeyMapDialog::PrintKeyMap  
 Bir kullanıcı tıkladığında çerçevesi tarafından çağrılır **yazdırma** düğmesi.  
  
```  
virtual void PrintKeyMap();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `PrintKeyMap` Yöntemi anahtarı eşleme yazdırır. Art arda çağırır ve yeni bir yazdırma işi başlatır [CMFCKeyMapDialog::OnPrintHeader](#onprintheader) ve [CMFCKeyMapDialog::OnPrintItem](#onprintitem) tüm anahtar eşlemelerinin yazdırılır kadar yöntemleri.  
  
##  <a name="setcolumnswidth"></a>  CMFCKeyMapDialog::SetColumnsWidth  
 Klavye eşleme denetimi destekleyen iç liste denetiminde sütunların genişliğini ayarlamak için çerçevesi tarafından çağrılır.  
  
```  
virtual void SetColumnsWidth();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem iç listesi denetimi sütunlarından varsayılan genişliğini ayarlar. Kısayol tuşları sütunun genişliği ilk olarak hesaplanır. Ardından kalan genişliğini üçte komutu sütuna ayrılır ve kalan iki üç açıklama sütuna ayrılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CKeyboardManager Sınıfı](../../mfc/reference/ckeyboardmanager-class.md)
