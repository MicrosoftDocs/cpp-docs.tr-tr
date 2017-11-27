---
title: "CMFCRibbonEdit sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CanBeStretched
- AFXRIBBONEDIT/CMFCRibbonEdit::CopyFrom
- AFXRIBBONEDIT/CMFCRibbonEdit::CreateEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::DestroyCtrl
- AFXRIBBONEDIT/CMFCRibbonEdit::DropDownList
- AFXRIBBONEDIT/CMFCRibbonEdit::EnableSpinButtons
- AFXRIBBONEDIT/CMFCRibbonEdit::GetCompactSize
- AFXRIBBONEDIT/CMFCRibbonEdit::GetEditText
- AFXRIBBONEDIT/CMFCRibbonEdit::GetIntermediateSize
- AFXRIBBONEDIT/CMFCRibbonEdit::GetTextAlign
- AFXRIBBONEDIT/CMFCRibbonEdit::GetWidth
- AFXRIBBONEDIT/CMFCRibbonEdit::HasCompactMode
- AFXRIBBONEDIT/CMFCRibbonEdit::HasFocus
- AFXRIBBONEDIT/CMFCRibbonEdit::HasLargeMode
- AFXRIBBONEDIT/CMFCRibbonEdit::HasSpinButtons
- AFXRIBBONEDIT/CMFCRibbonEdit::IsHighlighted
- AFXRIBBONEDIT/CMFCRibbonEdit::OnAfterChangeRect
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDraw
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDrawLabelAndImage
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDrawOnList
- AFXRIBBONEDIT/CMFCRibbonEdit::OnEnable
- AFXRIBBONEDIT/CMFCRibbonEdit::OnHighlight
- AFXRIBBONEDIT/CMFCRibbonEdit::OnKey
- AFXRIBBONEDIT/CMFCRibbonEdit::OnLButtonDown
- AFXRIBBONEDIT/CMFCRibbonEdit::OnLButtonUp
- AFXRIBBONEDIT/CMFCRibbonEdit::OnRTLChanged
- AFXRIBBONEDIT/CMFCRibbonEdit::OnShow
- AFXRIBBONEDIT/CMFCRibbonEdit::Redraw
- AFXRIBBONEDIT/CMFCRibbonEdit::SetACCData
- AFXRIBBONEDIT/CMFCRibbonEdit::SetEditText
- AFXRIBBONEDIT/CMFCRibbonEdit::SetTextAlign
- AFXRIBBONEDIT/CMFCRibbonEdit::SetWidth
dev_langs: C++
helpviewer_keywords:
- CMFCRibbonEdit [MFC], CMFCRibbonEdit
- CMFCRibbonEdit [MFC], CanBeStretched
- CMFCRibbonEdit [MFC], CMFCRibbonEdit
- CMFCRibbonEdit [MFC], CopyFrom
- CMFCRibbonEdit [MFC], CreateEdit
- CMFCRibbonEdit [MFC], DestroyCtrl
- CMFCRibbonEdit [MFC], DropDownList
- CMFCRibbonEdit [MFC], EnableSpinButtons
- CMFCRibbonEdit [MFC], GetCompactSize
- CMFCRibbonEdit [MFC], GetEditText
- CMFCRibbonEdit [MFC], GetIntermediateSize
- CMFCRibbonEdit [MFC], GetTextAlign
- CMFCRibbonEdit [MFC], GetWidth
- CMFCRibbonEdit [MFC], HasCompactMode
- CMFCRibbonEdit [MFC], HasFocus
- CMFCRibbonEdit [MFC], HasLargeMode
- CMFCRibbonEdit [MFC], HasSpinButtons
- CMFCRibbonEdit [MFC], IsHighlighted
- CMFCRibbonEdit [MFC], OnAfterChangeRect
- CMFCRibbonEdit [MFC], OnDraw
- CMFCRibbonEdit [MFC], OnDrawLabelAndImage
- CMFCRibbonEdit [MFC], OnDrawOnList
- CMFCRibbonEdit [MFC], OnEnable
- CMFCRibbonEdit [MFC], OnHighlight
- CMFCRibbonEdit [MFC], OnKey
- CMFCRibbonEdit [MFC], OnLButtonDown
- CMFCRibbonEdit [MFC], OnLButtonUp
- CMFCRibbonEdit [MFC], OnRTLChanged
- CMFCRibbonEdit [MFC], OnShow
- CMFCRibbonEdit [MFC], Redraw
- CMFCRibbonEdit [MFC], SetACCData
- CMFCRibbonEdit [MFC], SetEditText
- CMFCRibbonEdit [MFC], SetTextAlign
- CMFCRibbonEdit [MFC], SetWidth
ms.assetid: 9b85f1f2-446b-454e-9af9-104fdad8a897
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2aa9f57fd95f31181f62892349aff7d7223fd786
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcribbonedit-class"></a>CMFCRibbonEdit sınıfı
Şerit çubuğunda bulunan bir düzenleme denetimi uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonEdit : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|Oluşturan bir `CMFCRibbonEdit` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonEdit::CanBeStretched](#canbestretched)|Gösterir olup olmadığını yüksekliğini `CMFCRibbonEdit` denetim dikey bir Şerit satır yüksekliğini artırabilirsiniz.|  
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|Oluşturan bir `CMFCRibbonEdit` nesnesi.|  
|[CMFCRibbonEdit::CopyFrom](#copyfrom)|Belirtilen durumunu kopyalar `CMFCRibbonEdit` geçerli nesne `CMFCRibbonEdit` nesne.|  
|[CMFCRibbonEdit::CreateEdit](#createedit)|İçin yeni bir metin kutusu oluşturur `CMFCRibbonEdit` nesnesi.|  
|[CMFCRibbonEdit::DestroyCtrl](#destroyctrl)|Bozar `CMFCRibbonEdit` nesnesi.|  
|[CMFCRibbonEdit::DropDownList](#dropdownlist)|Bir liste kutusu bırakır.|  
|[CMFCRibbonEdit::EnableSpinButtons](#enablespinbuttons)|Değer değiştirme düğmesi metin kutusu için çeşitli ayarlar ve sağlar.|  
|[CMFCRibbonEdit::GetCompactSize](#getcompactsize)|Compact boyutunu alır `CFMCRibbonEdit` nesnesi.|  
|[CMFCRibbonEdit::GetEditText](#getedittext)|Metin kutusundaki metni alır.|  
|[CMFCRibbonEdit::GetIntermediateSize](#getintermediatesize)|Ara boyutunu alır `CMFCRibbonEdit` nesnesi.|  
|[CMFCRibbonEdit::GetTextAlign](#gettextalign)|Metin kutusundaki metin hizalamasını alır.|  
|[CMFCRibbonEdit::GetWidth](#getwidth)|Piksel cinsinden genişliği alır `CMFCRibbonEdit` denetim.|  
|[CMFCRibbonEdit::HasCompactMode](#hascompactmode)|Gösteren görüntü için boyut olup olmadığını `CMFCRibbonEdit` denetim compact olabilir.|  
|[CMFCRibbonEdit::HasFocus](#hasfocus)|Gösterir olup olmadığını `CMFCRIbbonEdit` denetimi odağa.|  
|[CMFCRibbonEdit::HasLargeMode](#haslargemode)|Gösteren görüntü için boyut olup olmadığını `CMFCRibbonEdit` denetim büyük olabilir.|  
|[CMFCRibbonEdit::HasSpinButtons](#hasspinbuttons)|Metin kutusuna bir değer değiştirme düğmesi olup olmadığını gösterir.|  
|[CMFCRibbonEdit::IsHighlighted](#ishighlighted)|Gösterir olup olmadığını `CMFCRibbonEdit` denetim vurgulanır.|  
|[CMFCRibbonEdit::OnAfterChangeRect](#onafterchangerect)|Çerçevesi tarafından çağrılır zaman boyutları için görüntü dikdörtgenin `CMFCRibbonEdit` denetim değişiklikleri.|  
|[CMFCRibbonEdit::OnDraw](#ondraw)|Çizmek için çerçevesi tarafından çağrılır `CMFCRibbonEdit` denetim.|  
|[CMFCRibbonEdit::OnDrawLabelAndImage](#ondrawlabelandimage)|Etiket çizme ve için görüntü framework tarafından çağrılan `CMFCRibbonEdit` denetim.|  
|[CMFCRibbonEdit::OnDrawOnList](#ondrawonlist)|Çizmek için çerçevesi tarafından çağrılır `CMFCRibbonEdit` komutları liste kutusu denetimi.|  
|[CMFCRibbonEdit::OnEnable](#onenable)|Etkinleştirmek veya devre dışı bırakmak için çerçevesi tarafından çağrılır `CMFCRibbonEdit` denetim.|  
|[CMFCRibbonEdit::OnHighlight](#onhighlight)|İşaretçinin girdiğinde veya sınırları bırakır çerçevesi tarafından çağrılır `CMFCRibbonEdit` denetim.|  
|[CMFCRibbonEdit::OnKey](#onkey)|Kullanıcı bir keytip bastığında çerçevesi tarafından çağrılır ve `CMFCRibbonEdit` denetimi odağa.|  
|[CMFCRibbonEdit::OnLButtonDown](#onlbuttondown)|Güncelleştirilecek çerçevesi tarafından çağrılır `CMFCRibbonEdit` kullanıcı denetimi sol fare düğmesini bastığında denetim.|  
|[CMFCRibbonEdit::OnLButtonUp](#onlbuttonup)|Kullanıcı sol fare düğmesini bıraktığında çerçevesi tarafından çağrılır.|  
|[CMFCRibbonEdit::OnRTLChanged](#onrtlchanged)|Güncelleştirilecek çerçevesi tarafından çağrılır `CMFCRibbonEdit` Düzen yönü değiştiğinde denetim.|  
|[CMFCRibbonEdit::OnShow](#onshow)|Göstermek veya gizlemek için çerçevesi tarafından çağrılır `CMFCRibbonEdit` denetim.|  
|[CMFCRibbonEdit::Redraw](#redraw)|Görüntüsünü güncelleştirmeleri `CMFCRibbonEdit` denetim.|  
|[CMFCRibbonEdit::SetACCData](#setaccdata)|Erişilebilirlik verilerini ayarlar `CMFCRibbonEdit` nesnesi.|  
|[CMFCRibbonEdit::SetEditText](#setedittext)|Metni metin kutusunda ayarlar.|  
|[CMFCRibbonEdit::SetTextAlign](#settextalign)|Metin kutusunda metin hizalamasını ayarlar.|  
|[CMFCRibbonEdit::SetWidth](#setwidth)|Metin kutusu genişliğini ayarlar `CMFCRibbonEdit` denetim.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl oluşturulacağını gösteren bir `CMFCRibbonEdit` nesnesi, döndürme düğmeleri düzenleme denetimi yanında göster ve düzenleme denetimi metin ayarlayın. Bu kod parçacığını parçası olan [MS Office 2007 Demo örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#7](../../mfc/reference/codesnippet/cpp/cmfcribbonedit-class_1.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxRibbonEdit.h  
  
##  <a name="canbestretched"></a>CMFCRibbonEdit::CanBeStretched  
 Gösterir olup olmadığını yüksekliğini [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetim dikey bir Şerit satır yüksekliğini artırabilirsiniz.  
  
```  
virtual BOOL CanBeStretched();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman döndürür `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="cmfcribbonedit"></a>CMFCRibbonEdit::CMFCRibbonEdit  
 Oluşturan bir [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesi.  
  
```  
CMFCRibbonEdit(
    UINT nID,  
    int nWidth,  
    LPCTSTR lpszLabel = NULL,  
    int nImage = -1);

CMFCRibbonEdit();
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nID`  
 Komut kimliği için `CMFCRibbonEdit` denetim.  
  
 [in]`nWidth`  
 Metin kutusunun piksel cinsinden genişliği `CMFCRibbonEdit` denetim.  
  
 [in]`lpszLabel`  
 Etiketi `CMFCRibbonEdit` denetim.  
  
 [in]`nImage`  
 Küçük resim için kullanılacak dizini `CMFCRibbonEdit` denetim. Küçük resimler koleksiyonunu üst Şerit kategoriye göre korunur.  
  
### <a name="remarks"></a>Açıklamalar  
 `CMFCRibbonEdit` Denetim büyük bir görüntü kullanmaz.  
  
##  <a name="copyfrom"></a>CMFCRibbonEdit::CopyFrom  
 Belirtilen durumunu kopyalar [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) geçerli nesneye [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesi.  
  
```  
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`src`  
 Kaynak `CMFCRibbonEdit` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 `src` Parametresi türü olmalıdır `CMFCRibbonEdit`.  
  
##  <a name="createedit"></a>CMFCRibbonEdit::CreateEdit  
 İçin yeni bir metin kutusu oluşturur [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesi.  
  
```  
virtual CMFCRibbonRichEditCtrl* CreateEdit(
    CWnd* pWndParent,  
    DWORD dwEditStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pWndParent`  
 Üst penceresi için bir işaretçi `CMFCRibbonEdit` nesnesi.  
  
 [in]`dwEditStyle`  
 Metin kutusunun stilini belirtir. İle açıklamalar bölümünde listelenen pencere stilleri birleştirebilirsiniz [denetim stilleri düzenlemek](http://msdn.microsoft.com/library/windows/desktop/bb775464) Windows SDK'ın açıklanmıştır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa yeni bir metin kutusu için bir işaretçi; Aksi takdirde `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel metin kutusu oluşturmak için bir türetilmiş sınıfta bu yöntemi geçersiz kılın.  
  
 Aşağıdaki uygulayabilirsiniz [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) bir metin kutusu için:  
  
- **WS_CHILD**  
  
- **WS_VISIBLE**  
  
- **WS_DISABLED**  
  
- **WS_GROUP**  
  
- **WS_TABSTOP**  
  
##  <a name="destroyctrl"></a>CMFCRibbonEdit::DestroyCtrl  
 Bozar [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesi.  
  
```  
virtual void DestroyCtrl();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="dropdownlist"></a>CMFCRibbonEdit::DropDownList  
 Bir liste kutusu bırakır.  
  
```  
virtual void DropDownList();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak bu yöntem hiçbir şey yapmaz. Açılan bir liste kutusu için bu yöntemi geçersiz kılın.  
  
##  <a name="enablespinbuttons"></a>CMFCRibbonEdit::EnableSpinButtons  
 Değer değiştirme düğmesi metin kutusu için çeşitli ayarlar ve sağlar.  
  
```  
void EnableSpinButtons(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nMin`  
 Değer değiştirme düğmesi en küçük değeri.  
  
 [in]`nMax`  
 Değer değiştirme düğmesi maksimum değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürme düğmelerini yukarı görüntülemek ve aşağı oka ve sabit bir değer kümesi taşımak kullanıcıların etkinleştirin.  
  
##  <a name="getcompactsize"></a>CMFCRibbonEdit::GetCompactSize  
 Compact boyutunu alır [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesi.  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Bir cihaz bağlamı için işaretçi `CMFCRibbonEdit` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Compact boyutu `CMFCRibbonEdit` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getedittext"></a>CMFCRibbonEdit::GetEditText  
 Metin kutusundaki metni alır.  
  
```  
CString GetEditText() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Metin kutusundaki metin.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getintermediatesize"></a>CMFCRibbonEdit::GetIntermediateSize  
 Ara boyutunu alır [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesi.  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Bir cihaz bağlamı için işaretçi `CMFCRibbonEdit` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ara boyutu `CMFCRibbonEdit` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gettextalign"></a>CMFCRibbonEdit::GetTextAlign  
 Metin kutusundaki metin hizalamasını alır.  
  
```  
int GetTextAlign() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Metin hizalama değeri numaralandırılır. Olası değerler için Açıklamalar bölümüne bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen değer aşağıdaki Düzenle denetim stilleri biridir:  
  
- **ES_LEFT** sol hizalama  
  
- **ES_CENTER** center hizalama  
  
- **Es_rıght** sağa hizalama  
  
 Bu stiller hakkında daha fazla bilgi için bkz: [denetim stilleri düzenlemek](http://msdn.microsoft.com/library/windows/desktop/bb775464).  
  
##  <a name="getwidth"></a>CMFCRibbonEdit::GetWidth  
 Piksel cinsinden genişliği alır [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetim.  
  
```  
int GetWidth(BOOL bInFloatyMode = FALSE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bInFloatyMode`  
 `TRUE`varsa `CMFCRibbonEdit` denetimidir kayan modunda; Aksi halde, `FALSE`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Piksel cinsinden genişliği, `CMFCRibbonEdit` denetim.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="hascompactmode"></a>CMFCRibbonEdit::HasCompactMode  
 Gösteren görüntü için boyut olup olmadığını [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetim compact olabilir.  
  
```  
virtual BOOL HasCompactMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman döndürür `TRUE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak bu yöntem her zaman döndürür `TRUE`. Görüntü boyutu compact olup olamayacağını göstermek için bu yöntemi geçersiz kılın.  
  
##  <a name="hasfocus"></a>CMFCRibbonEdit::HasFocus  
 Gösterir olup olmadığını [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimi odağa.  
  
```  
virtual BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`varsa `CMFCRibbonEdit` denetimi odağa; Aksi halde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="haslargemode"></a>CMFCRibbonEdit::HasLargeMode  
 Gösteren görüntü için boyut olup olmadığını [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetim büyük olabilir.  
  
```  
virtual BOOL HasLargeMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman döndürür `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak bu yöntem her zaman döndürür `FALSE`. Görüntü boyutu büyük olup olamayacağını göstermek için bu yöntemi geçersiz kılın.  
  
##  <a name="hasspinbuttons"></a>CMFCRibbonEdit::HasSpinButtons  
 Metin kutusuna bir değer değiştirme düğmesi olup olmadığını gösterir.  
  
```  
virtual BOOL HasSpinButtons() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`metin kutusuna bir değer değiştirme düğmesi varsa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ishighlighted"></a>CMFCRibbonEdit::IsHighlighted  
 Gösterir olup olmadığını [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetim vurgulanır.  
  
```  
virtual BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`varsa `CMFCRibbonEdit` denetimidir vurgulanan; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onafterchangerect"></a>CMFCRibbonEdit::OnAfterChangeRect  
 Çerçevesi tarafından çağrılır zaman boyutları için görüntü dikdörtgenin [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) kontrol Değiştir.  
  
```  
virtual void OnAfterChangeRect(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Bir cihaz bağlamı için işaretçi `CMFCRibbonEdit` denetim.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondraw"></a>CMFCRibbonEdit::OnDraw  
 Çizmek için çerçevesi tarafından çağrılır [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetim.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Bir cihaz bağlamı için işaretçi `CMFCRibbonEdit` denetim.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondrawlabelandimage"></a>CMFCRibbonEdit::OnDrawLabelAndImage  
 Etiket çizme ve için görüntü framework tarafından çağrılan [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetim.  
  
```  
virtual void OnDrawLabelAndImage(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Bir cihaz bağlamı için işaretçi `CMFCRibbonEdit` denetim.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondrawonlist"></a>CMFCRibbonEdit::OnDrawOnList  
 Çizmek için çerçevesi tarafından çağrılır [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) komutları liste kutusu denetimi.  
  
```  
virtual void OnDrawOnList(
    CDC* pDC,  
    CString strText,  
    int nTextOffset,  
    CRect rect,  
    BOOL bIsSelected,  
    BOOL bHighlighted);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Bir cihaz bağlamı için işaretçi `CMFCRibbonEdit` denetim.  
  
 [in]`strText`  
 Görüntülenecek metni [](../../mfc/reference/cmfcribbonedit-class.md "cmfcribbonedit sınıfı").  
  
 [in]`nTextOffset`  
 Liste kutusu görüntüleme metni için sol tarafındaki piksel cinsinden uzaklığı.  
  
 [in]`rect`  
 Görüntü dikdörtgeni `CMFCRibbonEdit` denetim.  
  
 [in]`bIsSelected`  
 Bu parametre kullanılmaz.  
  
 [in]`bHighlighted`  
 Bu parametre kullanılmaz.  
  
### <a name="remarks"></a>Açıklamalar  
 Komutları liste kutusu kullanıcıların hızlı erişim araç çubuğunu özelleştirme Şerit denetimleri görüntüler.  
  
##  <a name="onenable"></a>CMFCRibbonEdit::OnEnable  
 Etkinleştirmek veya devre dışı bırakmak için çerçevesi tarafından çağrılır [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetim.  
  
```  
virtual void OnEnable(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bEnable`  
 `TRUE`denetimi etkinleştirmek için; `FALSE` denetimini devre dışı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onhighlight"></a>CMFCRibbonEdit::OnHighlight  
 İşaretçinin girdiğinde veya sınırları bırakır çerçevesi tarafından çağrılır [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetim.  
  
```  
virtual void OnHighlight(BOOL bHighlight);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bHighlight`  
 `TRUE`İşaretçi sınırları içinde ise `CMFCRibbonEdit` kontrol; Aksi halde, `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onkey"></a>CMFCRibbonEdit::OnKey  
 Kullanıcı bir keytip bastığında çerçevesi tarafından çağrılır ve [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimi odağa.  
  
```  
virtual BOOL OnKey(BOOL bIsMenuKey);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bIsMenuKey`  
 `TRUE`açılır menü keytip görüntüler Aksi takdirde `FALSE`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Olay işlendi Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onlbuttondown"></a>CMFCRibbonEdit::OnLButtonDown  
 Güncelleştirilecek çerçevesi tarafından çağrılır [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) kullanıcı denetimi sol fare düğmesini bastığında denetim.  
  
```  
virtual void OnLButtonDown(CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`point`  
 Bu parametre kullanılmaz.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onlbuttonup"></a>CMFCRibbonEdit::OnLButtonUp  
 Kullanıcı sol fare düğmesini bıraktığında çerçevesi tarafından çağrılır.  
  
```  
virtual void OnLButtonUp(CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`point`  
 Bu parametre kullanılmaz.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onrtlchanged"></a>CMFCRibbonEdit::OnRTLChanged  
 Güncelleştirilecek çerçevesi tarafından çağrılır [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Düzen yönü değiştiğinde denetim.  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bIsRTL`  
 `TRUE`Düzen sağdan sola ise; `FALSE` düzeni soldan sağa ise.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onshow"></a>CMFCRibbonEdit::OnShow  
 Göstermek veya gizlemek için çerçevesi tarafından çağrılır [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetim.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bShow`  
 `TRUE`Denetim göstermek için; `FALSE` denetimi gizlemek için.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="redraw"></a>CMFCRibbonEdit::Redraw  
 Görüntüsünü güncelleştirmeleri [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetim.  
  
```  
virtual void Redraw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem için Görüntü dikdörtgen yeniden çizer `CMFCRibbonEdit` dolaylı olarak çağırarak nesne [CWnd::RedrawWindow](http://msdn.microsoft.com/library/windows/desktop/dd162911) ile `RDW_INVALIDATE`, `RDW_ERASE`, ve `RDW_UPDATENOW` bayrakları kümesi.  
  
##  <a name="setaccdata"></a>CMFCRibbonEdit::SetACCData  
 Erişilebilirlik verilerini ayarlar [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesi.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parametreler  
 `pParent`  
 İşaretçi üst penceresine `CMFCRibbonEdit` nesnesi.  
  
 `data`  
 Erişilebilirlik verilerini `CMFCRibbonEdit` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman döndürür `TRUE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setedittext"></a>CMFCRibbonEdit::SetEditText  
 Metni metin kutusunda ayarlar.  
  
```  
void SetEditText(CString strText);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`strText`  
 Metin kutusunda metin.  
  
##  <a name="settextalign"></a>CMFCRibbonEdit::SetTextAlign  
 Metin kutusunda metin hizalamasını ayarlar.  
  
```  
void SetTextAlign(int nAlign);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nAlign`  
 Metin hizalama değeri numaralandırılır. Olası değerler için Açıklamalar bölümüne bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametre `nAlign` aşağıdaki Düzenle denetim stilleri biridir:  
  
- **ES_LEFT** sol hizalama  
  
- **ES_CENTER** center hizalama  
  
- **Es_rıght** sağa hizalama  
  
 Bu stiller hakkında daha fazla bilgi için bkz: [denetim stilleri düzenlemek](http://msdn.microsoft.com/library/windows/desktop/bb775464).  
  
##  <a name="setwidth"></a>CMFCRibbonEdit::SetWidth  
 Metin kutusu genişliğini ayarlar [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetim.  
  
```  
void SetWidth(
    int nWidth,  
    BOOL bInFloatyMode = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nWidth`  
 Metin kutusunun piksel cinsinden genişliği.  
  
 `bInFloatyMode`  
 `TRUE`Kayan modu için genişliğini ayarlamak için; `FALSE` normal modu için genişliğini ayarlamak için.  
  
### <a name="remarks"></a>Açıklamalar  
 `CMFCRibbonEdit` Denetleyebilir, görüntü modu bağlı olarak iki genişlikleri: modu ve normal modu kayan.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonBar sınıfı](../../mfc/reference/cmfcribbonbar-class.md)