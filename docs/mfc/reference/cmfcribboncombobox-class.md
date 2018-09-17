---
title: CMFCRibbonComboBox sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68746d76c9c7842e9fc8c16addeca2cb44f31211
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45701746"
---
# <a name="cmfcribboncombobox-class"></a>CMFCRibbonComboBox sınıfı
`CMFCRibbonComboBox` Sınıfı bir Şerit çubuğuna, Şerit paneline veya Şerit açılır menüsüne ekleyebileceğiniz birleşik giriş kutusu denetimi uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonComboBox : public CMFCRibbonEdit  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="constructors"></a>Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonComboBox::CMFCRibbonComboBox](#cmfcribboncombobox)|CMFCRibbonComboBox bir nesne oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonComboBox::AddItem](#additem)|Liste kutusuna benzersiz bir öğe ekler.|  
|[CMFCRibbonComboBox::DeleteItem](#deleteitem)|Belirtilen öğe liste kutusundan siler.|  
|[CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)|Zaman doğru açılır liste kutusu boyutu değiştirip değiştiremeyeceğini belirtir.|  
|[CMFCRibbonComboBox::FindItem](#finditem)|Liste kutusunda belirtilen dizeyle eşleşip ilk öğenin dizinini döndürür.|  
|[CMFCRibbonComboBox::GetCount](#getcount)|Liste kutusundan öğe sayısını döndürür.|  
|[CMFCRibbonComboBox::GetCurSel](#getcursel)|Liste kutusunda seçili öğenin dizinini alır.|  
|[CMFCRibbonComboBox::GetDropDownHeight](#getdropdownheight)|Liste kutusu bırakıldığında liste kutusunun yüksekliğini alır.|  
|[CMFCRibbonComboBox::GetIntermediateSize](#getintermediatesize)|Birleşik giriş kutusunun boyutunu Ara modunda görüntülenen olarak döndürür.|  
|[CMFCRibbonComboBox::GetItem](#getitem)|Belirtilen bir dizinden liste kutusunda bir öğe ile ilişkili dizeyi döndürür.|  
|[CMFCRibbonComboBox::GetItemData](#getitemdata)|Belirtilen bir dizinden liste kutusunda bir öğe ile ilişkili verilerini döndürür.|  
|[CMFCRibbonComboBox::HasEditBox](#haseditbox)|Denetim bir düzenleme kutusuna içerip içermediğini belirtir.|  
|[CMFCRibbonComboBox::IsResizeDropDownList](#isresizedropdownlist)|Liste kutusu boyutlandırılabilir olup olmadığını gösterir.|  
|[CMFCRibbonComboBox::OnSelectItem](#onselectitem)|Kullanıcı bir öğeyi liste kutusunda seçtiğinde framework tarafından çağırılır.|  
|[CMFCRibbonComboBox::RemoveAllItems](#removeallitems)|Liste kutusundan tüm öğeleri siler ve düzenleme kutusuna temizler.|  
|[CMFCRibbonComboBox::SelectItem](#selectitem)|Liste kutusunda bir öğe seçer.|  
|[CMFCRibbonComboBox::SetDropDownHeight](#setdropdownheight)|Liste kutusunun yüksekliğini, bırakılan ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Statik etiket veya kullanıcı tarafından düzenlenebilen etiketi ile birleştirilmiş bir liste kutusunun Şerit birleşik giriş kutusu oluşur. Şerit combo box'ınızı oluşturduğunuzda hangi türünü belirtmeniz gerekir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCRibbonComboBox` sınıfı, birleşik giriş kutusu için bir öğe eklemek, birleşik giriş kutusunda bir öğe seçin ve bir paneline bir birleşik giriş kutusu ekleyin.  
  
 [!code-cpp[NVC_MFC_RibbonApp#11](../../mfc/reference/codesnippet/cpp/cmfcribboncombobox-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)  
  
 [CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxribboncombobox.h  
  
##  <a name="additem"></a>  CMFCRibbonComboBox::AddItem  
 Liste kutusuna benzersiz bir öğe ekler.  
  
```  
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>Parametreler  
*lpszItem*<br/>
[in] Eklenecek öğe dizisi.  
  
*dwData*<br/>
[in] Eklenecek öğe ile ilişkili veriler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eklenen öğe sıfır tabanlı dizini.  
  
##  <a name="cmfcribboncombobox"></a>  CMFCRibbonComboBox::CMFCRibbonComboBox  
 Oluşturur bir `CMFCRibbonComboBox` nesne.  
  
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
*nID*<br/>
[in] Birleşik giriş kutusu kimliği.  
  
*bHasEditBox*<br/>
[in] Düzenleme kutusu denetiminde istiyorsanız TRUE; FALSE Aksi takdirde.  
  
*nWidth*<br/>
[in] Birleşik giriş kutusu piksel cinsinden genişliği; veya varsayılan genişliğini için -1.  
  
*lpszLabel*<br/>
[in] Birleşik giriş kutusunun görünen etiket.  
  
*Bir*<br/>
[in] Birleşik giriş kutusu küçük resim dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan genişliğini 108 pikseldir.  
  
##  <a name="deleteitem"></a>  CMFCRibbonComboBox::DeleteItem  
 Belirtilen öğe liste kutusundan siler.  
  
```  
BOOL DeleteItem(int iIndex);
BOOL DeleteItem(DWORD_PTR dwData);

BOOL DeleteItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parametreler  
*İIndex*<br/>
[in] Silinecek öğenin sıfır tabanlı dizini.  
  
*dwData*<br/>
[in] Silinecek öğe ile ilişkili veriler.  
  
*lpszText*<br/>
[in] Silinecek öğe dizisi. Aynı dize ile birden çok öğe varsa, ilk öğe silindi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen öğe silindiyse TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="enabledropdownlistresize"></a>  CMFCRibbonComboBox::EnableDropDownListResize  
 Zaman doğru açılır liste kutusu boyutu değiştirip değiştiremeyeceğini belirtir.  
  
```  
void EnableDropDownListResize(BOOL bEnable=FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
*bSistemlerde*<br/>
[in] Etkinleştirme yeniden boyutlandırma için true; Yeniden boyutlandırma devre dışı bırakmak için FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeniden boyutlandırma etkinleştirildiğinde, liste kutusunun boyutu görüntülediği öğelerin uyacak şekilde değiştirir.  
  
##  <a name="finditem"></a>  CMFCRibbonComboBox::FindItem  
 Liste kutusunda belirtilen dizeyle eşleşip ilk öğenin dizinini döndürür.  
  
```  
int FindItem(LPCTSTR lpszText) const;  
```  
  
### <a name="parameters"></a>Parametreler  
*lpszText*<br/>
[in] Liste kutusunda bir öğe dizisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğenin sıfır tabanlı dizini; veya öğenin bulunamaması durumunda -1.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcount"></a>  CMFCRibbonComboBox::GetCount  
 Liste kutusundan öğe sayısını döndürür.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusu ya da liste kutusunun hiç öğe içeriyorsa, 0 öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcursel"></a>  CMFCRibbonComboBox::GetCurSel  
 Liste kutusunda seçili öğenin dizinini alır.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusunda seçili öğenin sıfır tabanlı dizini; veya hiçbir öğe seçili ise -1.  
  
##  <a name="getdropdownheight"></a>  CMFCRibbonComboBox::GetDropDownHeight  
 Liste kutusu bırakıldığında liste kutusunun yüksekliğini alır.  
  
```  
int GetDropDownHeight();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusu piksel cinsinden yüksekliği.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getintermediatesize"></a>  CMFCRibbonComboBox::GetIntermediateSize  
 Birleşik giriş kutusunun boyutunu Ara modunda görüntülenen olarak döndürür.  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
*pDC*<br/>
[in] Birleşik giriş kutusu için bir cihaz bağlamı işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Birleşik giriş kutusunun boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Küçük resimler görüntülediğinde döndürülen boyutla birleşik giriş kutusunun boyutu temel alınır.  
  
##  <a name="getitem"></a>  CMFCRibbonComboBox::GetItem  
 Belirtilen bir dizinden liste kutusunda bir öğe ile ilişkili dizeyi döndürür.  
  
```  
LPCTSTR GetItem(int iIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
*İIndex*<br/>
[in] Liste kutusunda bir öğenin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğesiyle ilişkili dize için bir işaretçi; Aksi takdirde NULL dizin parametresi geçersiz olması veya dizin parametresi -1'dir ve birleşik giriş kutusunda seçili öğe yok.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getitemdata"></a>  CMFCRibbonComboBox::GetItemData  
 Belirtilen bir dizinden liste kutusunda bir öğe ile ilişkili verilerini döndürür.  
  
```  
DWORD_PTR GetItemData(int iIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
*İIndex*<br/>
[in] Liste kutusunda bir öğenin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeyle ilişkili verileri; 0 veya öğe mevcut değil veya dizin parametresi -1'dir ve liste kutusunda seçili öğe yok.  
  
##  <a name="haseditbox"></a>  CMFCRibbonComboBox::HasEditBox  
 Denetim bir düzenleme kutusuna içerip içermediğini belirtir.  
  
```  
BOOL HasEditBox() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düzenleme kutusu denetim içeriyorsa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isresizedropdownlist"></a>  CMFCRibbonComboBox::IsResizeDropDownList  
 Liste kutusu boyutlandırılabilir olup olmadığını gösterir.  
  
```  
BOOL IsResizeDropDownList() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste kutusunun yeniden boyutlandırılabilir TRUE; Aksi durumda FALSE. [CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)  
  
### <a name="remarks"></a>Açıklamalar  
 Liste kutusunu kullanarak yeniden boyutlandırma etkinleştirebilirsiniz [CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize) yöntemi.  
  
##  <a name="onselectitem"></a>  CMFCRibbonComboBox::OnSelectItem  
 Bir kullanıcı bir öğeyi liste kutusunda seçtiğinde framework tarafından çağırılır.  
  
```  
virtual void OnSelectItem(int nItem);
```  
  
### <a name="parameters"></a>Parametreler  
*nItem*<br/>
[in] Seçilen öğenin dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kullanıcı giriş seçimi işlemek istiyorsanız bu yöntemi yok sayın.  
  
##  <a name="removeallitems"></a>  CMFCRibbonComboBox::RemoveAllItems  
 Liste kutusundan tüm öğeleri siler ve düzenleme kutusuna temizler.  
  
```  
void RemoveAllItems();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="selectitem"></a>  CMFCRibbonComboBox::SelectItem  
 Liste kutusunda bir öğe seçer.  
  
```  
BOOL SelectItem(int iIndex);
BOOL SelectItem(DWORD_PTR dwData);

BOOL SelectItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parametreler  
*İIndex*<br/>
[in] Liste kutusunda bir öğenin sıfır tabanlı dizini.  
  
*dwData*<br/>
[in] Liste kutusunda bir öğe ile ilişkili veriler.  
  
*lpszText*<br/>
[in] Liste kutusunda bir öğe dizisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olduysa TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setdropdownheight"></a>  CMFCRibbonComboBox::SetDropDownHeight  
 Liste kutusunun yüksekliğini, bırakılan ayarlar.  
  
```  
void SetDropDownHeight(int nHeight);
```  
  
### <a name="parameters"></a>Parametreler  
*nHeight*<br/>
[in] Liste kutusu piksel cinsinden yüksekliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan yükseklik 150 pikseldir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonEdit Sınıfı](../../mfc/reference/cmfcribbonedit-class.md)
