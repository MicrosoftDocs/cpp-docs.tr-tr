---
title: "CMFCRibbonComboBox sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::AddItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::DeleteItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::EnableDropDownListResize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::FindItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCount
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCurSel
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetDropDownHeight
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetIntermediateSize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItemData
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::HasEditBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::IsResizeDropDownList
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::OnSelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::RemoveAllItems
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SetDropDownHeight
dev_langs: C++
helpviewer_keywords:
- CMFCRibbonComboBox [MFC], CMFCRibbonComboBox
- CMFCRibbonComboBox [MFC], AddItem
- CMFCRibbonComboBox [MFC], DeleteItem
- CMFCRibbonComboBox [MFC], EnableDropDownListResize
- CMFCRibbonComboBox [MFC], FindItem
- CMFCRibbonComboBox [MFC], GetCount
- CMFCRibbonComboBox [MFC], GetCurSel
- CMFCRibbonComboBox [MFC], GetDropDownHeight
- CMFCRibbonComboBox [MFC], GetIntermediateSize
- CMFCRibbonComboBox [MFC], GetItem
- CMFCRibbonComboBox [MFC], GetItemData
- CMFCRibbonComboBox [MFC], HasEditBox
- CMFCRibbonComboBox [MFC], IsResizeDropDownList
- CMFCRibbonComboBox [MFC], OnSelectItem
- CMFCRibbonComboBox [MFC], RemoveAllItems
- CMFCRibbonComboBox [MFC], SelectItem
- CMFCRibbonComboBox [MFC], SetDropDownHeight
ms.assetid: 9b29a6a4-cf17-4152-9b13-0bf90784b30d
caps.latest.revision: "35"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9f748630549c0a26a2818bc7c96e5162d7d36ed4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcribboncombobox-class"></a>CMFCRibbonComboBox sınıfı
`CMFCRibbonComboBox` Sınıfı bir Şerit çubuğu, bir Şerit panel ya da Şerit açılan menüye ekleyebileceğiniz bir birleşik giriş kutusu denetimi uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonComboBox : public CMFCRibbonEdit  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="constructors"></a>Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonComboBox::CMFCRibbonComboBox](#cmfcribboncombobox)|CMFCRibbonComboBox nesnesi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonComboBox::AddItem](#additem)|Liste kutusu için benzersiz bir öğe ekler.|  
|[CMFCRibbonComboBox::DeleteItem](#deleteitem)|Belirtilen öğe liste kutusundan siler.|  
|[CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)|Liste kutusu bırakır zaman boyutu değiştirip değiştiremeyeceğini belirler.|  
|[CMFCRibbonComboBox::FindItem](#finditem)|Belirtilen bir dizeyle eşleşir liste kutusunda ilk öğenin dizinini döndürür.|  
|[CMFCRibbonComboBox::GetCount](#getcount)|Liste kutusunda öğe sayısını döndürür.|  
|[CMFCRibbonComboBox::GetCurSel](#getcursel)|Liste kutusunda seçili öğenin dizinini alır.|  
|[CMFCRibbonComboBox::GetDropDownHeight](#getdropdownheight)|Liste kutusunda bırakıldığında liste kutusu yüksekliğini alır.|  
|[CMFCRibbonComboBox::GetIntermediateSize](#getintermediatesize)|Birleşik giriş kutusu boyutunu Ara modunda görüntülendiği şekilde döndürür.|  
|[CMFCRibbonComboBox::GetItem](#getitem)|Liste kutusunda belirtilen dizindeki bir öğesiyle ilişkili dizeyi döndürür.|  
|[CMFCRibbonComboBox::GetItemData](#getitemdata)|Liste kutusunda belirtilen dizindeki bir öğesiyle ilişkili verileri döndürür.|  
|[CMFCRibbonComboBox::HasEditBox](#haseditbox)|Denetim düzenleme kutusu içerip içermediğini belirtir.|  
|[CMFCRibbonComboBox::IsResizeDropDownList](#isresizedropdownlist)|Liste kutusu yeniden boyutlandırılabilir olup olmadığını gösterir.|  
|[CMFCRibbonComboBox::OnSelectItem](#onselectitem)|Kullanıcı liste kutusunda bir öğe seçtiğinde çerçevesi tarafından çağrılır.|  
|[CMFCRibbonComboBox::RemoveAllItems](#removeallitems)|Tüm öğeleri liste kutusundan siler ve düzenleme kutusuna temizler.|  
|[CMFCRibbonComboBox::SelectItem](#selectitem)|Bir öğeyi liste kutusunda seçer.|  
|[CMFCRibbonComboBox::SetDropDownHeight](#setdropdownheight)|Bu bırakıldığında liste kutusu yüksekliğini ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir statik etiket veya kullanıcı tarafından düzenlenebilir etiketi ile birlikte bir liste kutusu Şerit birleşik giriş kutusu oluşur. Şerit birleşik giriş kutusu oluşturduğunuzda, istediğiniz hangi türünü belirtmeniz gerekir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCRibbonComboBox` sınıfı, bir öğe için açılan kutu eklemek, açılan kutuda bir öğe seçin ve bir paneline birleşik giriş kutusu ekleyin.  
  
 [!code-cpp[NVC_MFC_RibbonApp#11](../../mfc/reference/codesnippet/cpp/cmfcribboncombobox-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)  
  
 [CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxribboncombobox.h  
  
##  <a name="additem"></a>CMFCRibbonComboBox::AddItem  
 Liste kutusu için benzersiz bir öğe ekler.  
  
```  
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszItem`  
 Eklenecek öğe dizesi.  
  
 [in]`dwData`  
 Eklenecek öğe ile ilişkili veriler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eklenen öğenin sıfır tabanlı dizini.  
  
##  <a name="cmfcribboncombobox"></a>CMFCRibbonComboBox::CMFCRibbonComboBox  
 Oluşturan bir `CMFCRibbonComboBox` nesnesi.  
  
```  
public:  
CMFCRibbonComboBox(
    UINT nID,  
    BOOL bHasEditBox=TRUE,  
    Int nWidth=-1,  
    LPCTSTR lpszLabel=NULL,  
    Int nImage=-1);

protected:  
CMFCRibbonComboBox();
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nID`  
 Birleşik giriş kutusu kimliği.  
  
 [in]`bHasEditBox`  
 `TRUE`Denetim içinde düzenleme kutusu istiyorsanız; `FALSE` Aksi takdirde.  
  
 [in]`nWidth`  
 Birleşik giriş kutusu piksel cinsinden genişliği; veya varsayılan genişliği -1.  
  
 [in]`lpszLabel`  
 Birleşik giriş kutusu görünen etiket.  
  
 [in]`nImage`  
 Birleşik giriş kutusu küçük resim dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan genişliğini 108 pikseldir.  
  
##  <a name="deleteitem"></a>CMFCRibbonComboBox::DeleteItem  
 Belirtilen öğe liste kutusundan siler.  
  
```  
BOOL DeleteItem(int iIndex);
BOOL DeleteItem(DWORD_PTR dwData);

BOOL DeleteItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`iIndex`  
 Silinecek öğenin sıfır tabanlı dizini.  
  
 [in]`dwData`  
 Silinecek öğe ile ilişkili veriler.  
  
 [in]`lpszText`  
 Silinecek öğe dizesi. Aynı dize ile birden çok öğe varsa, ilk öğe silindi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Belirtilen öğe silinmişse; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="enabledropdownlistresize"></a>CMFCRibbonComboBox::EnableDropDownListResize  
 Liste kutusu bırakır zaman boyutu değiştirip değiştiremeyeceğini belirler.  
  
```  
void EnableDropDownListResize(BOOL bEnable=FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bEnable`  
 `TRUE`yeniden boyutlandırma etkinleştirmek için; `FALSE` yeniden boyutlandırma devre dışı bırakmak için.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeniden boyutlandırma etkinleştirildiğinde, liste kutusu boyutunu görüntülediği öğeleri uyacak şekilde değiştirin.  
  
##  <a name="finditem"></a>CMFCRibbonComboBox::FindItem  
 Belirtilen bir dizeyle eşleşir liste kutusunda ilk öğenin dizinini döndürür.  
  
```  
int FindItem(LPCTSTR lpszText) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszText`  
 Liste kutusunda bir öğe dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğenin sıfır tabanlı dizini; veya öğesi bulunmazsa -1.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcount"></a>CMFCRibbonComboBox::GetCount  
 Liste kutusunda öğe sayısını döndürür.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusu veya liste kutusu hiçbir öğe içeriyorsa 0 öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcursel"></a>CMFCRibbonComboBox::GetCurSel  
 Liste kutusunda seçili öğenin dizinini alır.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusunda seçili öğenin sıfır tabanlı dizini; veya hiçbir öğe seçili ise -1.  
  
##  <a name="getdropdownheight"></a>CMFCRibbonComboBox::GetDropDownHeight  
 Liste kutusunda bırakıldığında liste kutusu yüksekliğini alır.  
  
```  
int GetDropDownHeight();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusu piksel cinsinden yüksekliği.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getintermediatesize"></a>CMFCRibbonComboBox::GetIntermediateSize  
 Birleşik giriş kutusu boyutunu Ara modunda görüntülendiği şekilde döndürür.  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Birleşik giriş kutusu için bir cihaz bağlamı işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Birleşik giriş kutusu boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Küçük resimler görüntülediğinde döndürülen boyut birleşik giriş kutusu boyutuna dayanır.  
  
##  <a name="getitem"></a>CMFCRibbonComboBox::GetItem  
 Liste kutusunda belirtilen dizindeki bir öğesiyle ilişkili dizeyi döndürür.  
  
```  
LPCTSTR GetItem(int iIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`iIndex`  
 Liste kutusunda öğenin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeyle ilişkili dize için bir işaretçi; Aksi takdirde `NULL` dizin parametresi geçersiz olması veya dizin parametre -1'dir ve açılan kutuda seçili öğe yok.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getitemdata"></a>CMFCRibbonComboBox::GetItemData  
 Liste kutusunda belirtilen dizindeki bir öğesiyle ilişkili verileri döndürür.  
  
```  
DWORD_PTR GetItemData(int iIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`iIndex`  
 Liste kutusunda öğenin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu öğeyle ilişkili veri; ya da 0 öğe yoksa ya da dizin parametresi ise -1 ve liste kutusunda seçili öğe yok.  
  
##  <a name="haseditbox"></a>CMFCRibbonComboBox::HasEditBox  
 Denetim düzenleme kutusu içerip içermediğini belirtir.  
  
```  
BOOL HasEditBox() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Denetim düzenleme kutusu içeriyorsa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isresizedropdownlist"></a>CMFCRibbonComboBox::IsResizeDropDownList  
 Liste kutusu yeniden boyutlandırılabilir olup olmadığını gösterir.  
  
```  
BOOL IsResizeDropDownList() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Liste kutusu yeniden boyutlandırılabilir Aksi takdirde `FALSE`. [CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)  
  
### <a name="remarks"></a>Açıklamalar  
 Liste kutusunu kullanarak yeniden boyutlandırma etkinleştirebilirsiniz [CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize) yöntemi.  
  
##  <a name="onselectitem"></a>CMFCRibbonComboBox::OnSelectItem  
 Bir kullanıcı liste kutusunda bir öğe seçtiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual void OnSelectItem(int nItem);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nItem`  
 Seçili öğenin dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kullanıcı giriş seçimi işlemek istiyorsanız bu yöntemi geçersiz kılın.  
  
##  <a name="removeallitems"></a>CMFCRibbonComboBox::RemoveAllItems  
 Tüm öğeleri liste kutusundan siler ve düzenleme kutusuna temizler.  
  
```  
void RemoveAllItems();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="selectitem"></a>CMFCRibbonComboBox::SelectItem  
 Bir öğeyi liste kutusunda seçer.  
  
```  
BOOL SelectItem(int iIndex);
BOOL SelectItem(DWORD_PTR dwData);

BOOL SelectItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`iIndex`  
 Liste kutusunda öğenin sıfır tabanlı dizini.  
  
 [in]`dwData`  
 Liste kutusunda bir öğesiyle ilişkili veriler.  
  
 [in]`lpszText`  
 Liste kutusunda bir öğe dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setdropdownheight"></a>CMFCRibbonComboBox::SetDropDownHeight  
 Bu bırakıldığında liste kutusu yüksekliğini ayarlar.  
  
```  
void SetDropDownHeight(int nHeight);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nHeight`  
 Liste kutusu piksel cinsinden yüksekliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan yükseklik 150 pikseldir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonEdit Sınıfı](../../mfc/reference/cmfcribbonedit-class.md)
