---
title: CMFCRibbonSeparator sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::AddToListBox
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CopyFrom
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::GetRegularSize
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsTabStop
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDraw
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDrawOnList
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonSeparator [MFC], CMFCRibbonSeparator
- CMFCRibbonSeparator [MFC], AddToListBox
- CMFCRibbonSeparator [MFC], CopyFrom
- CMFCRibbonSeparator [MFC], GetRegularSize
- CMFCRibbonSeparator [MFC], IsSeparator
- CMFCRibbonSeparator [MFC], IsTabStop
- CMFCRibbonSeparator [MFC], OnDraw
- CMFCRibbonSeparator [MFC], OnDrawOnList
ms.assetid: bedb1a53-cb07-4c3c-be12-698c5409e7cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b1c4c3b286f020d8d409b344c5d8c05ebc200425
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370864"
---
# <a name="cmfcribbonseparator-class"></a>CMFCRibbonSeparator sınıfı
Şerit ayırıcı uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonSeparator : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCRibbonSeparator::CMFCRibbonSeparator](#cmfcribbonseparator)|Oluşturan bir `CMFCRibbonSeparator` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCRibbonSeparator::AddToListBox](#addtolistbox)|Bir ayırıcı ekler **komutları** listesinde **Özelleştir** iletişim kutusu. (Geçersiz kılmaları [CMFCRibbonBaseElement::AddToListBox](../../mfc/reference/cmfcribbonbaseelement-class.md#addtolistbox).)|  
|`CMFCRibbonSeparator::CreateObject`|Bu sınıf türü dinamik bir örneğini oluşturmak için framework tarafından kullanıldı.|  
|`CMFCRibbonSeparator::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCRibbonSeparator::CopyFrom](#copyfrom)|Ayırıcı 's üye değişkenleri başka bir nesneden ayarlar kopyalama yöntemi.|  
|[CMFCRibbonSeparator::GetRegularSize](#getregularsize)|Ayırıcı boyutu döndürür.|  
|[CMFCRibbonSeparator::IsSeparator](#isseparator)|Bu bir ayırıcı olup olmadığını gösterir.|  
|[CMFCRibbonSeparator::IsTabStop](#istabstop)|Bu sekme durağı olup olmadığını gösterir.|  
|[CMFCRibbonSeparator::OnDraw](#ondraw)|Şerit veya hızlı erişim araç ayırıcı çizmek için sistem tarafından çağrılır.|  
|[CMFCRibbonSeparator::OnDrawOnList](#ondrawonlist)|Ayırıcı çizileceğini sistem tarafından çağrılan **komutları** listesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Şerit ayırıcı mantıksal olarak ayırır öğeleri Şerit, dikey veya yatay çizgi ' dir. Ayırıcı Şerit denetimi, ana uygulama menüsü, Şerit durum çubuğu ve hızlı erişim araç çizilebilir.  
  
 Uygulamanızda bir ayırıcı kullanmak için yeni nesnesi oluşturun ve aşağıda gösterildiği gibi ana uygulama menüsüne ekleyin:  
  
```  
CMFCRibbonMainPanel* pMainPanel = m_wndRibbonBar.AddMainCategory(_T("Main Menu"),
    IDB_FILESMALL,
    IDB_FILELARGE);

...  
pMainPanel->Add(new CMFCRibbonSeparator(TRUE));
```  
Çağrı [CMFCRibbonPanel::AddSeparator](../../mfc/reference/cmfcribbonpanel-class.md#addseparator) Şerit bölmeleri ayırıcısı eklemek için. Ayırıcılar ayrılmış ve tarafından dahili olarak eklenen `AddSeparator` yöntemi.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSeparator](../../mfc/reference/cmfcribbonseparator-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxbaseribbonelement.h  
  
##  <a name="addtolistbox"></a>  CMFCRibbonSeparator::AddToListBox  
 Bir ayırıcı ekler **komutları** listesinde **Özelleştir** iletişim kutusu.  
  
```  
virtual int AddToListBox(
    CMFCRibbonCommandsListBox* pWndListBox,  
    BOOL bDeep);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pWndListBox`  
 Bir işaretçi **komutları** liste ayırıcı burada eklenir.  
  
 [in] `bDeep`  
 Yoksayıldı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır tabanlı dizini tarafından belirtilen liste kutusunda dizeye `pWndListBox`.  
  
##  <a name="cmfcribbonseparator"></a>  CMFCRibbonSeparator::CMFCRibbonSeparator  
 Oluşturan bir `CMFCRibbonSeparator` nesnesi.  
  
```  
CMFCRibbonSeparator(BOOL bIsHoriz = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bIsHoriz`  
 Varsa `TRUE`, ayırıcı yataydır if `FALSE`, ayırıcı dikeydir.  
  
### <a name="remarks"></a>Açıklamalar  
 Yatay ayırıcılar uygulama menülerde kullanılır. Dikey ayırıcılar araç çubuklarını kullanılır.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCRibbonSeparator` sınıfı.  
  
 [!code-cpp[NVC_MFC_RibbonApp#19](../../mfc/reference/codesnippet/cpp/cmfcribbonseparator-class_1.cpp)]  
  
##  <a name="copyfrom"></a>  CMFCRibbonSeparator::CopyFrom  
 Ayırıcı 's üye değişkenleri başka bir nesneden ayarlar kopyalama yöntemi.  
  
```  
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `Src`  
 Kopyalanacak kaynak Şerit öğesi.  
  
##  <a name="getregularsize"></a>  CMFCRibbonSeparator::GetRegularSize  
 Ayırıcı boyutu döndürür.  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Bir aygıt içerik için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Verilen cihaz bağlamı ayırıcı boyutu.  
  
##  <a name="isseparator"></a>  CMFCRibbonSeparator::IsSeparator  
 Bu bir ayırıcı olup olmadığını gösterir.  
  
```  
virtual BOOL IsSeparator() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman `TRUE` Bu sınıf için.  
  
##  <a name="istabstop"></a>  CMFCRibbonSeparator::IsTabStop  
 Bu sekme durağı olup olmadığını gösterir.  
  
```  
virtual BOOL IsTabStop() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman `FALSE` Bu sınıf için.  
  
### <a name="remarks"></a>Açıklamalar  
 Şerit ayırıcı sekme durağı değil.  
  
##  <a name="ondraw"></a>  CMFCRibbonSeparator::OnDraw  
 Şerit veya hızlı erişim araç ayırıcı çizmek için sistem tarafından çağrılır.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
##  <a name="ondrawonlist"></a>  CMFCRibbonSeparator::OnDrawOnList  
 Ayırıcı çizileceğini sistem tarafından çağrılan **komutları** listesi.  
  
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
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in] `pDC`|Bir cihaz bağlamı için bir işaretçi.|  
|[in] `strText`|Listede görüntülenecek metin.|  
|[in] `nTextOffset`|Metin ve sınırlayıcı dikdörtgenini sol tarafındaki arasındaki aralık.|  
|[in] `rect`|Sınırlayıcı dikdörtgenini belirtir.|  
|[in] `bIsSelected`|Yoksayıldı.|  
|[in] `bHighlighted`|Yoksayıldı.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıflar](../../mfc/reference/mfc-classes.md)
