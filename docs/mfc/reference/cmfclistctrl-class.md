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
ms.openlocfilehash: 04eccb2d1472afb1c04daac8ab23c2ce6fe97c58
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37851452"
---
# <a name="cmfclistctrl-class"></a>CMFCListCtrl sınıfı
`CMFCListCtrl` Sınıf işlevselliğini genişleten [CListCtrl sınıfı](../../mfc/reference/clistctrl-class.md) Gelişmiş üstbilgi denetim işlevini destekleyerek sınıfı [CMFCHeaderCtrl sınıfı](../../mfc/reference/cmfcheaderctrl-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCListCtrl : public CListCtrl  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCListCtrl::EnableMarkSortedColumn](#enablemarksortedcolumn)|Farklı bir arka plan rengi ile sıralanmış bir sütun olarak işaretlemek eklemenize imkan tanır.|  
|[CMFCListCtrl::EnableMultipleSort](#enablemultiplesort)|Birden çok sıralama modunu etkinleştirir.|  
|[CMFCListCtrl::GetHeaderCtrl](#getheaderctrl)|Altı çizili üstbilgi denetimine bir başvuru döndürür.|  
|[CMFCListCtrl::IsMultipleSort](#ismultiplesort)|Liste denetimi birden çok sıralama modunda olup olmadığını denetler.|  
|[CMFCListCtrl::OnCompareItems](#oncompareitems)|İki liste denetimi öğeleri karşılaştırmalıdır framework tarafından çağırılır.|  
|[CMFCListCtrl::OnGetCellBkColor](#ongetcellbkcolor)|Tek bir hücre arka plan rengini belirlemelisiniz framework tarafından çağırılır.|  
|[CMFCListCtrl::OnGetCellFont](#ongetcellfont)|Yazı tipini çizilen hücre edinmeniz gerekir framework tarafından çağırılır.|  
|[CMFCListCtrl::OnGetCellTextColor](#ongetcelltextcolor)|Tek bir hücre metin rengi belirlemelisiniz framework tarafından çağırılır.|  
|[CMFCListCtrl::RemoveSortColumn](#removesortcolumn)|Sıralama sütunu sıralanmış sütunlar listesinden kaldırır.|  
|[CMFCListCtrl::SetSortColumn](#setsortcolumn)|Geçerli sıralanmış sütunu ve sıralama düzenini ayarlar.|  
|[CMFCListCtrl::Sort](#sort)|Listesi denetimini sıralar.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CMFCListCtrl` iki iyileştirme sunar [CListCtrl sınıfı](../../mfc/reference/clistctrl-class.md) sınıfı. İlk olarak, bu sütun sıralama mevcut bir seçeneği otomatik olarak bir sıralama ok başlığında çizerek olduğunu gösterir. İkinci olarak, aynı anda birden çok sütun üzerinde sıralama verilerini destekler.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, çeşitli yöntemlerin nasıl kullanılacağını gösterir `CMFCListCtrl` sınıfı. Örneğin, liste denetimi oluşturma, sütun ekleme, öğe eklemek, bir öğenin metni ayarlama ve liste denetimi yazı tipini Ayarla gösterilmektedir. Bu kod parçacığı parçasıdır [Visual Studio gösterim örneği](../../visual-cpp-samples.md).  
  
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
 Farklı bir arka plan rengi ile sıralanmış sütunlar işaretler.  
  
```  
void EnableMarkSortedColumn(
    BOOL bMark = TRUE,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bMark*  
 Farklı bir arka plan rengi etkinleştirilip etkinleştirilmeyeceğini belirleyen bir Boole parametresi.  
  
 [in] *bRedraw*  
 Denetim hemen yeniden çizmek etkinleştirilip etkinleştirilmeyeceğini belirleyen bir Boole parametresi.  
  
### <a name="remarks"></a>Açıklamalar  
 `EnableMarkSortedColumn` yöntemini kullanan `CDrawingManager::PixelAlpha` sıralanan sütunlar ne için kullanılacak rengi hesaplamak için. Çekilen rengi düzenli arka plan rengini alır.  
  
##  <a name="enablemultiplesort"></a>  CMFCListCtrl::EnableMultipleSort  
 Liste denetimi veri satırlarını birden çok sütuna göre sıralama sağlar.  
  
```  
void EnableMultipleSort(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bSistemlerde*  
 Birden çok sütunu sıralama modu etkinleştirilip etkinleştirilmeyeceğini belirleyen bir Boole değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Birden çok sütuna göre sıralama etkinleştirdiğinizde, sütunları bir hiyerarşi içerir. Veri satırı öncelikle birincil sütuna göre sıralanır. Herhangi bir eşdeğer değeri, ardından öncelik sırasına göre her bir sonraki sütuna göre sıralanır.  
  
##  <a name="getheaderctrl"></a>  CMFCListCtrl::GetHeaderCtrl  
 Üstbilgi denetimine bir başvuru döndürür.  
  
```  
virtual CMFCHeaderCtrl& GetHeaderCtrl();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Temel bir başvuru [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md) nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Sütun başlıklarını içeren bir pencere bir list denetimi için başlık denetimidir. Ayrıca, doğrudan sütunları genellikle konumlandırıldı.  
  
##  <a name="ismultiplesort"></a>  CMFCListCtrl::IsMultipleSort  
 Liste denetimi şu anda üzerinde birden çok sütunu sıralamayı destekleyip desteklemediğini denetler.  
  
```  
BOOL IsMultipleSort() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste denetimi birden çok sıralama destekliyorsa TRUE; FALSE Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Olduğunda bir [CMFCListCtrl sınıfı](../../mfc/reference/cmfclistctrl-class.md) destekleyen birden çok sıralama, kullanıcının liste denetimi verilerde birden çok sütunlara göre sıralayabilirsiniz. Birden çok sıralamayı etkinleştirmek için çağrı [CMFCListCtrl::EnableMultipleSort](#enablemultiplesort).  
  
##  <a name="oncompareitems"></a>  CMFCListCtrl::OnCompareItems  
 İki öğeleri karşılaştırırken framework bu yöntemi çağırır.  
  
```  
virtual int OnCompareItems(
    LPARAM lParam1,  
    LPARAM lParam2,  
    int iColumn);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lParam1*  
 Karşılaştırılacak ilk öğe.  
  
 [in] *lParam2*  
 Karşılaştırılacak ikinci öğe.  
  
 [in] *iColumn*  
 Bu yöntem sıralama sütunu dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İki öğenin göreli konumunu belirten bir tamsayı. Negatif bir değer gösterir: ikinci ilk öğenin önünde, ilk öğe ikinci izlemelisiniz ve sıfır iki öğeyi eşdeğer olduğu anlamına gelir. pozitif bir değer gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama her zaman 0 değerini döndürür. Sıralama algoritması sağlamak için bu işlevi geçersiz kılmanız gerekir.  
  
##  <a name="ongetcellbkcolor"></a>  CMFCListCtrl::OnGetCellBkColor  
 Framework bu yöntemi çağırır tek bir hücre arka plan rengini belirlemeniz gerekir.  
  
```  
virtual COLORREF OnGetCellBkColor(
    int nRow,  
    int nColumn);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nRow*  
 Söz konusu hücrenin satır.  
  
 [in] *nColumn*  
 Söz konusu hücrenin sütun.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hücre arka plan rengini belirten bir COLOREF değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulaması `OnGetCellBkColor` sağlanan giriş parametrelerini kullanmaz ve bunun yerine yalnızca çağıran `GetBkColor`. Bu nedenle varsayılan olarak, aynı arka plan rengi tüm liste denetimi olacaktır. Geçersiz kılabilirsiniz `OnGetCellBkColor` ayrı arka plan rengi ile tek tek hücrelere işaretlemek için türetilen bir sınıfta.  
  
##  <a name="ongetcellfont"></a>  CMFCListCtrl::OnGetCellFont  
 Tek bir hücre yazı tipini aldığında framework bu yöntemi çağırır.  
  
```  
virtual HFONT OnGetCellFont(
    int nRow,  
    int nColumn,  
    DWORD dwData = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nRow*  
 Söz konusu hücrenin satır.  
  
 [in] *nColumn*  
 Söz konusu hücrenin sütun.  
  
 [in] *dwData*  
 Kullanıcı tanımlı veri. Varsayılan uygulama, bu parametre kullanmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli hücreyi için kullanılan yazı tipi için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu yöntem NULL döndürür. Liste denetiminde hücrelerin tümü aynı yazı tipi sahip. Farklı bir yazı tipi farklı hücresini sağlamak için bu yöntemi yok sayın.  
  
##  <a name="ongetcelltextcolor"></a>  CMFCListCtrl::OnGetCellTextColor  
 Framework bu yöntemi çağırır tek bir hücre metin rengi belirlemeniz gerekir.  
  
```  
virtual COLORREF OnGetCellTextColor(
    int nRow,  
    int nColumn);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nRow*  
 Söz konusu hücrenin satır.  
  
 [in] *nColumn*  
 Söz konusu hücrenin sütun.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hücre rengini belirten bir COLOREF değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu yöntemin çağırdığı `GetTextColor` giriş parametrelerini ne olursa olsun. Tam liste denetimi aynı metin rengini olacaktır. Geçersiz kılabilirsiniz `OnGetCellTextColor` ayrı metin rengi ile tek tek hücrelere işaretlemek için türetilen bir sınıfta.  
  
##  <a name="removesortcolumn"></a>  CMFCListCtrl::RemoveSortColumn  
 Sıralama sütunu sıralanmış sütunlar listesinden kaldırır.  
  
```  
void RemoveSortColumn(int iColumn);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *iColumn*  
 Kaldırmak için sütun.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem bir sıralama sütunu üstbilgisi denetiminden kaldırır. Çağrı [CMFCHeaderCtrl::RemoveSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#removesortcolumn).  
  
##  <a name="setsortcolumn"></a>  CMFCListCtrl::SetSortColumn  
 Geçerli sıralanmış sütunu ve sıralama düzenini ayarlar.  
  
```  
void SetSortColumn(
    int iColumn,  
    BOOL bAscending = TRUE,  
    BOOL bAdd = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *iColumn*  
 Sıralanacak sütunu.  
  
 [in] *bAscending*  
 Sıralama düzenini belirten bir Boole değeri.  
  
 [in] *bekle*  
 Yöntemi tarafından belirtilen sütun ekler olup olmadığını belirten Boolean bir değer *iColumn* sütunları sıralama listesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, yöntemi kullanarak üstbilgi denetimine giriş parametrelerini geçirir [CMFCHeaderCtrl::SetSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#setsortcolumn).  
  
##  <a name="sort"></a>  CMFCListCtrl::Sort  
 Listesi denetimini sıralar.  
  
```  
virtual void Sort(
    int iColumn,  
    BOOL bAscending = TRUE,  
    BOOL bAdd = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *iColumn*  
 Sıralanacak sütunu.  
  
 [in] *bAscending*  
 Sıralama düzenini belirten bir Boole değeri.  
  
 [in] *bekle*  
 Bu yöntem tarafından belirtilen sütun ekler olup olmadığını belirten Boolean bir değer *iColumn* sütunları sıralama listesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CListCtrl Sınıfı](../../mfc/reference/clistctrl-class.md)
