---
title: "CMFCRibbonUndoButton sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::AddUndoAction
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CleanUpUndoList
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::GetActionNumber
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::HasMenu
dev_langs: C++
helpviewer_keywords:
- CMFCRibbonUndoButton [MFC], CMFCRibbonUndoButton
- CMFCRibbonUndoButton [MFC], AddUndoAction
- CMFCRibbonUndoButton [MFC], CleanUpUndoList
- CMFCRibbonUndoButton [MFC], GetActionNumber
- CMFCRibbonUndoButton [MFC], HasMenu
ms.assetid: 5c42adf7-871d-4239-901e-47ae7fb816fc
caps.latest.revision: "35"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f7d59d91f82a0fa86efcae7214874e0b2ca16a12
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcribbonundobutton-class"></a>CMFCRibbonUndoButton sınıfı
`CMFCRibbonUndoButton` Sınıfı en son kullanıcı komutlarını içeren bir açılan liste düğmesi uygular. Kullanıcılar, bir veya daha fazla en son komut Yinele ya da bunları geri almak için aşağı açılan listeden seçebilirsiniz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonUndoButton : public CMFCRibbonGallery  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonUndoButton::CMFCRibbonUndoButton](#cmfcribbonundobutton)|Yeni bir oluşturur `CMFCRibbonUndoButton` belirttiğiniz komut kimliği, metin etiketi ve üst nesne görüntü listesinden görüntü kullanarak nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonUndoButton::AddUndoAction](#addundoaction)|Yeni bir eylem Eylemler listesine ekler.|  
|[CMFCRibbonUndoButton::CleanUpUndoList](#cleanupundolist)|Aşağı açılan listesi olan eylem listesini temizler.|  
|[CMFCRibbonUndoButton::GetActionNumber](#getactionnumber)|Aşağı açılan listeden bir kullanıcı seçili öğe sayısını belirler.|  
|[CMFCRibbonUndoButton::HasMenu](#hasmenu)|Nesne bir menü içerip içermediğini belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CMFCRibbonUndoButton` Sınıfı aşağı açılan liste temsil edecek bir yığın kullanır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCRibbonUndoButton` sınıfı ve yeni bir eylem Eylemler listesine ekleyin. Bu kod parçacığını parçası olan [Şerit araçları örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_RibbonGadgets#2](../../mfc/reference/codesnippet/cpp/cmfcribbonundobutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
 [CMFCRibbonUndoButton](../../mfc/reference/cmfcribbonundobutton-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxribbonundobutton.h  
  
##  <a name="addundoaction"></a>CMFCRibbonUndoButton::AddUndoAction  
 Yeni bir eylem Eylemler listesine ekler.  
  
```  
void AddUndoAction(LPCTSTR lpszLabel);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszLabel`  
 Aşağı açılan liste görünümünde görüntülenen eylem etiketi.  
  
##  <a name="cleanupundolist"></a>CMFCRibbonUndoButton::CleanUpUndoList  
 Aşağı açılan listesi olan eylem listesini temizler.  
  
```  
void CleanUpUndoList();
```  
  
##  <a name="cmfcribbonundobutton"></a>CMFCRibbonUndoButton::CMFCRibbonUndoButton  
 Yeni bir oluşturur `CMFCRibbonUndoButton` belirttiğiniz komut kimliği, metin etiketi ve üst nesne görüntü listesinden görüntü kullanarak nesne.  
  
```  
CMFCRibbonUndoButton(
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex=-1,  
    int nLargeImageIndex=-1);

 
CMFCRibbonUndoButton(
    UINT nID,  
    LPCTSTR lpszText,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nID`  
 Komut tanımlayıcısını belirtir.  
  
 [in]`lpszText`  
 Düğme metni etiketini belirtir.  
  
 [in]`nSmallImageIndex`  
 Üst nesne düğmenin küçük görüntü için görüntü listesi içindeki sıfır tabanlı dizin.  
  
 [in]`nLargeImageIndex`  
 Üst nesne için görüntü listesi içindeki sıfır tabanlı dizin düğmenin büyük görüntünün.  
  
 [in]`hIcon`  
 Düğmenin resim olarak kullanabileceğiniz bir simge için bir tanıtıcı.  
  
##  <a name="getactionnumber"></a>CMFCRibbonUndoButton::GetActionNumber  
 Aşağı açılan listeden bir kullanıcı seçili öğe sayısını belirler.  
  
```  
int GetActionNumber() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir kullanıcı seçili öğe sayısı.  
  
##  <a name="hasmenu"></a>CMFCRibbonUndoButton::HasMenu  
 Nesne bir menü içerip içermediğini belirtir.  
  
```  
virtual BOOL HasMenu() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman döndürür `TRUE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonGallery sınıfı](../../mfc/reference/cmfcribbongallery-class.md)   
 [CMFCRibbonButton sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)
