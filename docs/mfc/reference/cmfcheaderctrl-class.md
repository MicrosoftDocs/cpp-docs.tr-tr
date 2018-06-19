---
title: CMFCHeaderCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl::CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl::EnableMultipleSort
- AFXHEADERCTRL/CMFCHeaderCtrl::GetColumnState
- AFXHEADERCTRL/CMFCHeaderCtrl::GetSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::IsAscending
- AFXHEADERCTRL/CMFCHeaderCtrl::IsDialogControl
- AFXHEADERCTRL/CMFCHeaderCtrl::IsMultipleSort
- AFXHEADERCTRL/CMFCHeaderCtrl::RemoveSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::SetSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::OnDrawItem
- AFXHEADERCTRL/CMFCHeaderCtrl::OnDrawSortArrow
- AFXHEADERCTRL/CMFCHeaderCtrl::OnFillBackground
dev_langs:
- C++
helpviewer_keywords:
- CMFCHeaderCtrl [MFC], CMFCHeaderCtrl
- CMFCHeaderCtrl [MFC], EnableMultipleSort
- CMFCHeaderCtrl [MFC], GetColumnState
- CMFCHeaderCtrl [MFC], GetSortColumn
- CMFCHeaderCtrl [MFC], IsAscending
- CMFCHeaderCtrl [MFC], IsDialogControl
- CMFCHeaderCtrl [MFC], IsMultipleSort
- CMFCHeaderCtrl [MFC], RemoveSortColumn
- CMFCHeaderCtrl [MFC], SetSortColumn
- CMFCHeaderCtrl [MFC], OnDrawItem
- CMFCHeaderCtrl [MFC], OnDrawSortArrow
- CMFCHeaderCtrl [MFC], OnFillBackground
ms.assetid: 2f5fbf7b-5c75-42db-9216-640b1628f777
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3a1c10cd6242f2845d64965d914093455da21c8a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370035"
---
# <a name="cmfcheaderctrl-class"></a>CMFCHeaderCtrl sınıfı
`CMFCHeaderCtrl` Sınıfı, üstbilgi denetimindeki birden çok sütun sıralama destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCHeaderCtrl : public CHeaderCtrl  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCHeaderCtrl::CMFCHeaderCtrl](#cmfcheaderctrl)|Oluşturan bir `CMFCHeaderCtrl` nesnesi.|  
|`CMFCHeaderCtrl::~CMFCHeaderCtrl`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort)|Etkinleştirir veya devre dışı bırakır *birden çok sütun sıralama* geçerli üstbilgi denetimi için modu.|  
|[CMFCHeaderCtrl::GetColumnState](#getcolumnstate)|Bir sütun sıralı veya artan veya azalan düzende sıralanmış olup olmadığını gösterir.|  
|[CMFCHeaderCtrl::GetSortColumn](#getsortcolumn)|Üstbilgi denetimi ilk sıralanmış sütununun sıfır tabanlı dizinini alır.|  
|`CMFCHeaderCtrl::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|[CMFCHeaderCtrl::IsAscending](#isascending)|Üstbilgi denetimi herhangi bir sütunu artan düzende sıralandı olup olmadığını gösterir.|  
|[CMFCHeaderCtrl::IsDialogControl](#isdialogcontrol)|Geçerli üstbilgi denetimi ana pencereyi bir iletişim kutusu olup olmadığını gösterir.|  
|[CMFCHeaderCtrl::IsMultipleSort](#ismultiplesort)|Geçerli üstbilgi denetimi içinde olup olmadığını belirten *birden çok sütun sıralama* modu.|  
|[CMFCHeaderCtrl::RemoveSortColumn](#removesortcolumn)|Belirtilen sütun sıralama sütunlar listesinden kaldırır.|  
|[CMFCHeaderCtrl::SetSortColumn](#setsortcolumn)|Belirtilen bir sütunun sıralama düzenini üstbilgi denetimindeki ayarlar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCHeaderCtrl::OnDrawItem](#ondrawitem)|Üstbilgi denetimi sütun çizmek için çerçevesi tarafından çağrılır.|  
|[CMFCHeaderCtrl::OnDrawSortArrow](#ondrawsortarrow)|Sıralama oku çizmek için çerçevesi tarafından çağrılır.|  
|[CMFCHeaderCtrl::OnFillBackground](#onfillbackground)|Üstbilgi denetimi sütunun arka doldurmak için çerçevesi tarafından çağrılır.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCHeaderCtrl` sınıfı ve nasıl etkinleştirileceği *birden çok sütun sıralama* geçerli üstbilgi denetimi için modu.  
  
 [!code-cpp[NVC_MFC_RibbonApp#24](../../mfc/reference/codesnippet/cpp/cmfcheaderctrl-class_1.cpp)]  
  
## <a name="remarks"></a>Açıklamalar  
 `CMFCHeaderCtrl` Sınıfı sütun sıralı olduğunu belirtmek için bir üstbilgi denetim Sütun sıralama ok çizer. Kullanım *birden çok sütun sıralama* modundaysa üst liste denetiminde sütun kümesini ( [CMFCListCtrl sınıfı](../../mfc/reference/cmfclistctrl-class.md)) aynı anda sıralanabilir.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)  
  
 [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxheaderctrl.h  
  
##  <a name="cmfcheaderctrl"></a>  CMFCHeaderCtrl::CMFCHeaderCtrl  
 Oluşturan bir `CMFCHeaderCtrl` nesnesi.  
  
```  
CMFCHeaderCtrl::CMFCHeaderCtrl()  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu oluşturucu, belirtilen değerler aşağıdaki üye değişkenleri başlatır:  
  
|Üye değişkeni|Değer|  
|---------------------|-----------|  
|`m_bIsMousePressed`|`FALSE`|  
|`m_bMultipleSort`|`FALSE`|  
|`m_bAscending`|`TRUE`|  
|`m_nHighlightedItem`|-1|  
|`m_bTracked`|`FALSE`|  
|`m_bIsDlgControl`|`FALSE`|  
|`m_hFont`|`NULL`|  
  
##  <a name="enablemultiplesort"></a>  CMFCHeaderCtrl::EnableMultipleSort  
 Etkinleştirir veya devre dışı bırakır *birden çok sütun sıralama* geçerli üstbilgi denetimi için modu.  
  
```  
void EnableMultipleSort(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bEnable`  
 `TRUE` birden çok sütun sıralama modunu etkinleştirmek için; `FALSE` birden çok sütun sıralama modu devre dışı bırakmak ve herhangi bir sütunu sıralanmış sütunlar listesinden kaldırmak için. Varsayılan değer `TRUE` şeklindedir.  
  
### <a name="remarks"></a>Açıklamalar  
 Etkinleştirmek veya birden çok sütun sıralama modu devre dışı bırakmak için bu yöntemi kullanın. Üstbilgi denetimi birden çok sütun sıralama modunda değilse, iki veya daha fazla sütun bir sıralamada katılabilirsiniz.  
  
##  <a name="getcolumnstate"></a>  CMFCHeaderCtrl::GetColumnState  
 Bir sütun sıralanmamış veya artan veya azalan düzende sıralanmış olup olmadığını gösterir.  
  
```  
int GetColumnState(int iColumn) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `iColumn`  
 Bir sütunun sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen sütun sıralama durumunu gösteren bir değer. Olası değerler aşağıdaki tabloda listelenmektedir:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|-1|Azalan düzende sıralanır.|  
|0|Sıralı değil.|  
|1.|Artan düzende sıralanır.|  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getsortcolumn"></a>  CMFCHeaderCtrl::GetSortColumn  
 Üstbilgi denetimi ilk sıralanmış sütununun sıfır tabanlı dizinini alır.  
  
```  
int GetSortColumn() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıralanmış bir sütun ya da hiç sıralanmış sütunu bulunursa, -1 dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Üstbilgi denetimi ise *birden çok sütun sıralama* modu ve bu yöntem, onaylar ve kullanmak için öneren uygulama hata ayıklama modunda derlenmiş [CMFCHeaderCtrl::GetColumnState](#getcolumnstate) yöntemi yerine. Üstbilgi denetimi birden çok sütun sıralama modda ise ve perakende modunda uygulama derlenmiş, bu yöntem -1 döndürür.  
  
##  <a name="isascending"></a>  CMFCHeaderCtrl::IsAscending  
 Üstbilgi denetimi herhangi bir sütunu artan düzende sıralandı olup olmadığını gösterir.  
  
```  
BOOL IsAscending() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Üstbilgi denetimi herhangi bir sütunu artan düzende sıralanır Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemin döndürdüğü değer üstbilgi denetim öğesi üzerinde uygun sıralama okunu görüntülemek için kullanılır. Kullanım [CMFCHeaderCtrl::SetSortColumn](#setsortcolumn) sırayı belirlemek için yöntem.  
  
##  <a name="isdialogcontrol"></a>  CMFCHeaderCtrl::IsDialogControl  
 Geçerli üstbilgi denetimi ana pencereyi bir iletişim kutusu olup olmadığını gösterir.  
  
```  
BOOL IsDialogControl() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Geçerli üstbilgi denetimi ana pencereyi bir iletişim kutusu Aksi takdirde `FALSE`.  
  
##  <a name="ismultiplesort"></a>  CMFCHeaderCtrl::IsMultipleSort  
 Geçerli üstbilgi denetimi içinde olup olmadığını belirten *birden çok sütun sıralama* modu.  
  
```  
BOOL IsMultipleSort() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` birden çok sütun sıralama modu etkinleştirildiğinde; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort) etkinleştirmek veya birden çok sütun sıralama modu devre dışı bırakmak için bir yöntem. Üstbilgi denetimi birden çok sütun sıralama modunda değilse, iki veya daha fazla sütun bir sıralamada katılabilirsiniz.  
  
##  <a name="ondrawitem"></a>  CMFCHeaderCtrl::OnDrawItem  
 Üstbilgi denetimi sütun çizmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDrawItem(
    CDC* pDC,  
    int iItem,  
    CRect rect,  
    BOOL bIsPressed,  
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] `iItem`  
 Çizmek için öğenin sıfır tabanlı dizini.  
  
 [in] `rect`  
 Sınırlayıcı dikdörtgen çizmek için öğesinin.  
  
 [in] `bIsPressed`  
 `TRUE` öğe basılı durumda çizmek için; Aksi takdirde `FALSE`.  
  
 [in] `bIsHighlighted`  
 `TRUE` Vurgulanan durumda öğesi çizmek için; Aksi takdirde `FALSE`.  
  
##  <a name="ondrawsortarrow"></a>  CMFCHeaderCtrl::OnDrawSortArrow  
 Sıralama oku çizmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDrawSortArrow(
    CDC* pDC,  
    CRect rectArrow);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] `rectArrow`  
 Sıralama oku sınırlayıcı dikdörtgenini.  
  
##  <a name="onfillbackground"></a>  CMFCHeaderCtrl::OnFillBackground  
 Üstbilgi denetimi sütunun arka doldurmak için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnFillBackground(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removesortcolumn"></a>  CMFCHeaderCtrl::RemoveSortColumn  
 Belirtilen sütun sıralama sütunlar listesinden kaldırır.  
  
```  
void RemoveSortColumn(int iColumn);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `iColumn`  
 Kaldırmak için sütunun sıfır tabanlı dizini.  
  
##  <a name="setsortcolumn"></a>  CMFCHeaderCtrl::SetSortColumn  
 Belirtilen bir sütunun sıralama düzenini üstbilgi denetimindeki ayarlar.  
  
```  
void SetSortColumn(
    int iColumn,  
    BOOL bAscending=TRUE,  
    BOOL bAdd=FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `iColumn`  
 Üstbilgi denetimi sütunun sıfır tabanlı dizini. Bu parametre küçükse sıfır, bu yöntem tüm sütunları sıralama sütunlar listesinden kaldırır.  
  
 [in] `bAscending`  
 Sütunun sıralama düzenini belirtir, `iColumn` parametresi belirtir. `TRUE` artan ayarlamak için; `FALSE` azalan ayarlamak için. Varsayılan değer `TRUE` şeklindedir.  
  
 [in] `bAdd`  
 `TRUE` için sütunun sıralama düzenini ayarlama `iColumn` parametresi belirtir.  
  
 Geçerli üstbilgi denetimi ise *birden çok sütun sıralama* modu, bu yöntem, belirtilen sütunun sütunları sıralama listesine ekler. Kullanım [CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort) birden çok sütun sıralama modu ayarlamak için.  
  
 Birden çok sütun sıralama modu ayarlı değildir ve bu yöntem, hata ayıklama modunda derlenmiş, bu yöntem onaylar. Birden çok sütun sıralama modu ayarlı değildir ve bu yöntem perakende modunda derlenmiş varsa, bu yöntem ilk tüm sütunları sıralama sütunlar listesinden kaldırır ve sonra belirtilen sütun listesine ekler.  
  
 `FALSE` İlk için tüm sütunları sıralama sütunlar listesinden kaldırın ve sonra belirtilen sütun listesine ekleyin. Varsayılan değer `FALSE` şeklindedir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir sütunun sıralama düzenini ayarlamak için bu yöntemi kullanın. Gerekirse, bu yöntem Sütun sıralama sütunlar listesine ekler. Üstbilgi denetimi yukarı veya aşağı işaret eden bir sıralama ok çizmek için sıralama düzenini kullanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCListCtrl Sınıfı](../../mfc/reference/cmfclistctrl-class.md)
