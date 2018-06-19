---
title: CMFCListCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCListCtrl
- AFXLISTCTRL/CMFCListCtrl
- AFXLISTCTRL/CMFCListCtrl::EnableMarkSortedColumn
- AFXLISTCTRL/CMFCListCtrl::EnableMultipleSort
- AFXLISTCTRL/CMFCListCtrl::GetHeaderCtrl
- AFXLISTCTRL/CMFCListCtrl::IsMultipleSort
- AFXLISTCTRL/CMFCListCtrl::OnCompareItems
- AFXLISTCTRL/CMFCListCtrl::OnGetCellBkColor
- AFXLISTCTRL/CMFCListCtrl::OnGetCellFont
- AFXLISTCTRL/CMFCListCtrl::OnGetCellTextColor
- AFXLISTCTRL/CMFCListCtrl::RemoveSortColumn
- AFXLISTCTRL/CMFCListCtrl::SetSortColumn
- AFXLISTCTRL/CMFCListCtrl::Sort
dev_langs:
- C++
helpviewer_keywords:
- CMFCListCtrl [MFC], EnableMarkSortedColumn
- CMFCListCtrl [MFC], EnableMultipleSort
- CMFCListCtrl [MFC], GetHeaderCtrl
- CMFCListCtrl [MFC], IsMultipleSort
- CMFCListCtrl [MFC], OnCompareItems
- CMFCListCtrl [MFC], OnGetCellBkColor
- CMFCListCtrl [MFC], OnGetCellFont
- CMFCListCtrl [MFC], OnGetCellTextColor
- CMFCListCtrl [MFC], RemoveSortColumn
- CMFCListCtrl [MFC], SetSortColumn
- CMFCListCtrl [MFC], Sort
ms.assetid: 50d16aee-138c-4f34-8690-cb75d544ef2e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 495bf2a3eab9ceee4ca0bab337d590c1820905e8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369628"
---
# <a name="cmfclistctrl-class"></a>CMFCListCtrl sınıfı
`CMFCListCtrl` Sınıfını genişleten işlevselliğini [CListCtrl sınıfı](../../mfc/reference/clistctrl-class.md) Gelişmiş üstbilgi denetim işlevselliğini destekleyen tarafından sınıfı [CMFCHeaderCtrl sınıfı](../../mfc/reference/cmfcheaderctrl-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCListCtrl : public CListCtrl  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCListCtrl::EnableMarkSortedColumn](#enablemarksortedcolumn)|Farklı arka plan rengiyle sıralanmış bir sütun olarak işaretlemek sağlar.|  
|[CMFCListCtrl::EnableMultipleSort](#enablemultiplesort)|Birden çok sıralama modu sağlar.|  
|[CMFCListCtrl::GetHeaderCtrl](#getheaderctrl)|Altı çizili üstbilgi denetimi için bir başvuru döndürür.|  
|[CMFCListCtrl::IsMultipleSort](#ismultiplesort)|Liste denetimi birden çok sıralama modunda olup olmadığını denetler.|  
|[CMFCListCtrl::OnCompareItems](#oncompareitems)|İki liste denetim öğeleri karşılaştırmanız gerekir çerçevesi tarafından çağrılır.|  
|[CMFCListCtrl::OnGetCellBkColor](#ongetcellbkcolor)|Tek bir hücre arka plan rengini belirlemelisiniz çerçevesi tarafından çağrılır.|  
|[CMFCListCtrl::OnGetCellFont](#ongetcellfont)|Çizilen hücre yazı tipini edinmelidir çerçevesi tarafından çağrılır.|  
|[CMFCListCtrl::OnGetCellTextColor](#ongetcelltextcolor)|Tek bir hücre metin rengi belirlemelisiniz çerçevesi tarafından çağrılır.|  
|[CMFCListCtrl::RemoveSortColumn](#removesortcolumn)|Sıralama sütunu sıralanmış sütunlar listesinden kaldırır.|  
|[CMFCListCtrl::SetSortColumn](#setsortcolumn)|Geçerli sıralanan sütunu ve sıralama düzenini ayarlar.|  
|[CMFCListCtrl::Sort](#sort)|Liste denetimi sıralar.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CMFCListCtrl` iki geliştirmeleri sunan [CListCtrl sınıfı](../../mfc/reference/clistctrl-class.md) sınıfı. İlk olarak, bu sütun sıralama kullanılabilir bir seçenek otomatik olarak bir sıralama ok başlığındaki çizerek olduğunu gösterir. İkinci olarak, aynı anda birden çok sütuna sıralama veri destekler.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli yöntemlerle kullanımı gösterilmiştir `CMFCListCtrl` sınıfı. Örneğin, liste denetimi oluşturma, sütun ekleme, öğe eklemek, bir öğenin metni ayarlama ve liste denetimi yazı tipini ayarlama gösterilmektedir. Bu kod parçacığını parçası olan [Visual Studio gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#25](../../mfc/codesnippet/cpp/cmfclistctrl-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#26](../../mfc/codesnippet/cpp/cmfclistctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListCtrl](../../mfc/reference/clistctrl-class.md)  
  
 [CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxlistctrl.h  
  
##  <a name="enablemarksortedcolumn"></a>  CMFCListCtrl::EnableMarkSortedColumn  
 Sıralanmış sütunları farklı arka plan rengiyle işaretler.  
  
```  
void EnableMarkSortedColumn(
    BOOL bMark = TRUE,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bMark`  
 Farklı arka plan rengi etkinleştirilip etkinleştirilmeyeceğini belirleyen bir Boolean parametresiyle.  
  
 [in] `bRedraw`  
 Denetim hemen yeniden boyutlandırmaya edilip edilmeyeceğini belirler Boole parametresi.  
  
### <a name="remarks"></a>Açıklamalar  
 `EnableMarkSortedColumn` bir yöntem `CDrawingManager::PixelAlpha` ne için kullanılacak rengi hesaplamak için sütunlar sıralanır. Çekilen renk düzenli arka plan rengi temel alır.  
  
##  <a name="enablemultiplesort"></a>  CMFCListCtrl::EnableMultipleSort  
 Liste denetiminde veri satırı birden çok sütuna göre sıralama sağlar.  
  
```  
void EnableMultipleSort(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bEnable`  
 Birden çok sütun sıralama modu etkinleştirilip etkinleştirilmeyeceğini belirten bir Boole değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Birden çok sütuna göre sıralama etkinleştirdiğinizde, sütuna bir hiyerarşiye sahip. Veri satırı ilk birincil sütuna göre sıralanır. Tüm eşdeğer değerleri sonra öncelik sırasına göre sonraki her sütuna göre sıralanır.  
  
##  <a name="getheaderctrl"></a>  CMFCListCtrl::GetHeaderCtrl  
 Üstbilgi denetimi için bir başvuru döndürür.  
  
```  
virtual CMFCHeaderCtrl& GetHeaderCtrl();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Arka plandaki başvuru [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md) nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste denetimi üstbilgi denetimi sütun başlıklarını içeren bir penceredir. Genellikle doğrudan sütunlarının üstünde yer alır.  
  
##  <a name="ismultiplesort"></a>  CMFCListCtrl::IsMultipleSort  
 Liste denetimi şu anda birden çok sütuna sıralamayı destekleyip desteklemediğini denetler.  
  
```  
BOOL IsMultipleSort() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Liste denetimi birden çok sıralama destekliyorsa; `FALSE` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman bir [CMFCListCtrl sınıfı](../../mfc/reference/cmfclistctrl-class.md) birden çok sıralama, destekleyen kullanıcı liste denetimi verilerde birden çok sütuna göre sıralama yapabilirsiniz. Birden çok sıralamayı etkinleştirmek için çağrı [CMFCListCtrl::EnableMultipleSort](#enablemultiplesort).  
  
##  <a name="oncompareitems"></a>  CMFCListCtrl::OnCompareItems  
 İki öğeyi karşılaştırır zaman çerçevesi bu yöntemi çağırır.  
  
```  
virtual int OnCompareItems(
    LPARAM lParam1,  
    LPARAM lParam2,  
    int iColumn);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lParam1`  
 Karşılaştırma yapılacak ilk öğe.  
  
 [in] `lParam2`  
 Karşılaştırılacak ikinci öğe.  
  
 [in] `iColumn`  
 Bu yöntem sıralama sütun dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İki öğeyi göreli konumunu belirten bir tamsayı. Negatif bir değer gösterir ilk öğeyi ikinci gelmelidir, ilk öğe ikinci uymalı ve sıfır iki öğeyi eşdeğer olduğu anlamına gelir. pozitif bir değer gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama her zaman 0 döndürür. Sıralama algoritması sağlamak için bu işlevi geçersiz kılmanız gerekir.  
  
##  <a name="ongetcellbkcolor"></a>  CMFCListCtrl::OnGetCellBkColor  
 Tek bir hücre arka plan rengini belirlemelisiniz zaman çerçevesi bu yöntemi çağırır.  
  
```  
virtual COLORREF OnGetCellBkColor(
    int nRow,  
    int nColumn);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `nRow`  
 Söz konusu hücre satır.  
  
 [in] `nColumn`  
 Söz konusu hücre sütun.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `COLOREF` hücre arka plan rengini belirten değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulaması `OnGetCellBkColor` sağlanan giriş parametreleri kullanmaz ve bunun yerine yalnızca çağırır `GetBkColor`. Bu nedenle, varsayılan olarak, tüm liste denetimi aynı arka plan rengi olacaktır. Geçersiz kılabilirsiniz `OnGetCellBkColor` ayrı ayrı arka plan rengi hücrelerle işaretlemek için bir türetilmiş sınıfta.  
  
##  <a name="ongetcellfont"></a>  CMFCListCtrl::OnGetCellFont  
 Tek bir hücre yazı tipini aldığında framework bu yöntemi çağırır.  
  
```  
virtual HFONT OnGetCellFont(
    int nRow,  
    int nColumn,  
    DWORD dwData = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `nRow`  
 Söz konusu hücre satır.  
  
 [in] `nColumn`  
 Söz konusu hücre sütun.  
  
 [in] `dwData`  
 Kullanıcı tanımlı veri. Varsayılan uygulama, bu parametre kullanmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli hücreyi için kullanılan yazı tipi için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu yöntem `NULL`. Liste denetimi hücrelerde aynı yazı tipini sahip. Farklı bir yazı tipi farklı hücresini sağlamak için bu yöntemi geçersiz kılın.  
  
##  <a name="ongetcelltextcolor"></a>  CMFCListCtrl::OnGetCellTextColor  
 Tek bir hücre metin rengi belirlemelisiniz zaman çerçevesi bu yöntemi çağırır.  
  
```  
virtual COLORREF OnGetCellTextColor(
    int nRow,  
    int nColumn);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `nRow`  
 Söz konusu hücre satır.  
  
 [in] `nColumn`  
 Söz konusu hücre sütun.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `COLOREF` hücresi metin rengi belirten değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu yöntemi çağırır `GetTextColor` giriş parametreleri ne olursa olsun. Tam liste denetimi aynı metin rengini sahip olur. Geçersiz kılabilirsiniz `OnGetCellTextColor` ayrı ayrı metin rengi hücrelerle işaretlemek için bir türetilmiş sınıfta.  
  
##  <a name="removesortcolumn"></a>  CMFCListCtrl::RemoveSortColumn  
 Sıralama sütunu sıralanmış sütunlar listesinden kaldırır.  
  
```  
void RemoveSortColumn(int iColumn);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `iColumn`  
 Kaldırmak için sütun.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem bir sıralama sütunu üstbilgi denetiminden kaldırır. Çağırır [CMFCHeaderCtrl::RemoveSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#removesortcolumn).  
  
##  <a name="setsortcolumn"></a>  CMFCListCtrl::SetSortColumn  
 Geçerli sıralanan sütunu ve sıralama düzenini ayarlar.  
  
```  
void SetSortColumn(
    int iColumn,  
    BOOL bAscending = TRUE,  
    BOOL bAdd = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `iColumn`  
 Sıralamak için sütun.  
  
 [in] `bAscending`  
 Sıralama düzenini belirten bir Boole değeri.  
  
 [in] `bAdd`  
 Yöntemi tarafından belirtilen sütun ekler olup olmadığını belirten bir Boole değeri `iColumn` sütunları sıralama listesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, yöntemi kullanarak üstbilgi denetimine giriş parametrelerini geçirir [CMFCHeaderCtrl::SetSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#setsortcolumn).  
  
##  <a name="sort"></a>  CMFCListCtrl::Sort  
 Liste denetimi sıralar.  
  
```  
virtual void Sort(
    int iColumn,  
    BOOL bAscending = TRUE,  
    BOOL bAdd = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `iColumn`  
 Sıralamak için sütun.  
  
 [in] `bAscending`  
 Sıralama düzenini belirten bir Boole değeri.  
  
 [in] `bAdd`  
 Bu yöntem tarafından belirtilen sütun ekler olup olmadığını belirten bir Boole değeri `iColumn` sütunları sıralama listesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CListCtrl Sınıfı](../../mfc/reference/clistctrl-class.md)
