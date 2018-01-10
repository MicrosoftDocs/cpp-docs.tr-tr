---
title: "CVSListBox sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CVSListBox
- AFXVSLISTBOX/CVSListBox
- AFXVSLISTBOX/CVSListBox::CVSListBox
- AFXVSLISTBOX/CVSListBox::AddItem
- AFXVSLISTBOX/CVSListBox::EditItem
- AFXVSLISTBOX/CVSListBox::GetCount
- AFXVSLISTBOX/CVSListBox::GetItemData
- AFXVSLISTBOX/CVSListBox::GetItemText
- AFXVSLISTBOX/CVSListBox::GetSelItem
- AFXVSLISTBOX/CVSListBox::RemoveItem
- AFXVSLISTBOX/CVSListBox::SelectItem
- AFXVSLISTBOX/CVSListBox::SetItemData
- AFXVSLISTBOX/CVSListBox::GetListHwnd
dev_langs: C++
helpviewer_keywords:
- CVSListBox [MFC], CVSListBox
- CVSListBox [MFC], AddItem
- CVSListBox [MFC], EditItem
- CVSListBox [MFC], GetCount
- CVSListBox [MFC], GetItemData
- CVSListBox [MFC], GetItemText
- CVSListBox [MFC], GetSelItem
- CVSListBox [MFC], RemoveItem
- CVSListBox [MFC], SelectItem
- CVSListBox [MFC], SetItemData
- CVSListBox [MFC], GetListHwnd
ms.assetid: c79be7b4-46ed-4af8-a41e-68962782d8ef
caps.latest.revision: "30"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f97d55b0b23302920e71dfd35766bfa0a4294d97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cvslistbox-class"></a>CVSListBox sınıfı
`CVSListBox` Sınıfı, bir düzenlenebilir bir liste denetimini destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CVSListBox : public CVSListBoxBase  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CVSListBox::CVSListBox](#cvslistbox)|Oluşturan bir `CVSListBox` nesnesi.|  
|`CVSListBox::~CVSListBox`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CVSListBox::AddItem](#additem)|Bir dize için bir liste denetimini ekler. (Geçersiz kılmaları `CVSListBoxBase::AddItem`.)|  
|[CVSListBox::EditItem](#edititem)|Liste Denetim öğesi metni düzenleme işlemi başlatır. (Geçersiz kılmaları `CVSListBoxBase::EditItem`.)|  
|[CVSListBox::GetCount](#getcount)|Bir düzenlenebilir bir liste denetimini dizelerde sayısını alır. (Geçersiz kılmaları `CVSListBoxBase::GetCount`.)|  
|[CVSListBox::GetItemData](#getitemdata)|Düzenlenebilir bir liste denetim öğesi ile ilişkilendirilen bir uygulamaya özgü 32-bit değeri alır. (Geçersiz kılmaları `CVSListBoxBase::GetItemData`.)|  
|[CVSListBox::GetItemText](#getitemtext)|Düzenlenebilir bir liste denetimini öğenin metnini alır. (Geçersiz kılmaları `CVSListBoxBase::GetItemText`.)|  
|[CVSListBox::GetSelItem](#getselitem)|Düzenlenebilir bir liste denetiminde seçili öğenin sıfır tabanlı dizinini alır. (Geçersiz kılmaları `CVSListBoxBase::GetSelItem`.)|  
|`CVSListBox::PreTranslateMessage`|Pencere iletileri için gönderilen önce çevirir [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) ve [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows çalışır. Daha fazla bilgi ve yöntem sözdizimi için bkz: [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Geçersiz kılmaları `CVSListBoxBase::PreTranslateMessage`.)|  
|[CVSListBox::RemoveItem](#removeitem)|Düzenlenebilir bir liste denetiminden öğeyi kaldırır. (Geçersiz kılmaları `CVSListBoxBase::RemoveItem`.)|  
|[CVSListBox::SelectItem](#selectitem)|Düzenlenebilir bir liste denetimini dizisi seçer. (Geçersiz kılmaları `CVSListBoxBase::SelectItem`.)|  
|[CVSListBox::SetItemData](#setitemdata)|Bir uygulamaya özgü 32-bit değeri bir düzenlenebilir liste denetim öğesi ile ilişkilendirir. (Geçersiz kılmaları `CVSListBoxBase::SetItemData`.)|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CVSListBox::GetListHwnd](#getlisthwnd)|Tanıtıcı geçerli katıştırılmış liste görünümü denetimi döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CVSListBox` Sınıfı, bir dizi oluşturmak, değiştirmek, silmek veya liste denetimindeki öğeleri yeniden düzenlemek kullanıcı etkinleştirme Düzenle düğmesi sağlar.  
  
 Düzenlenebilir liste denetimi resmini verilmiştir. "Item2" başlıklı ikinci liste girdisini düzenlemek için seçilir.  
  
 ![CVSListBox denetimi](../../mfc/reference/media/cvslistbox.png "cvslistbox")  
  
 Düzenlenebilir bir liste denetim eklemek için kaynak Düzenleyicisi'ni kullanırsanız dikkat **araç** Düzenleyicisi bölmesinde, önceden tanımlanmış düzenlenebilir liste denetimi sağlamaz. Bunun yerine, statik denetim gibi ekleme **grup kutusu** denetim. Çerçeve boyutunu ve düzenlenebilir liste denetimi konumunu belirtmek için bir yer tutucu olarak statik denetimi kullanır.  
  
 Bir iletişim kutusu şablonunda düzenlenebilir liste denetimi kullanmak için bildirmelidir bir `CVSListBox` iletişim kutusu sınıfınızda değişken. Değişkeni ve Denetim arasındaki veri değişimini desteklemek için tanımlarsınız bir `DDX_Control` makrosu girişi `DoDataExchange` iletişim kutusunun yöntemi. Varsayılan olarak, düzenlenebilir liste denetimi Düzenle düğmeleri oluşturulur. Düzen düğmelerini etkinleştirmek için devralınan CVSListBoxBase::SetStandardButtons yöntemini kullanın.  
  
 Örnekler dizini daha fazla bilgi için bkz: `New Controls` örnek, Page3.cpp ve Page3.h dosyaları.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CStatic](../../mfc/reference/cstatic-class.md)  
  
 `CVSListBoxBase`  
  
 [CVSListBox](../../mfc/reference/cvslistbox-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxvslistbox.h  
  
##  <a name="additem"></a>CVSListBox::AddItem  
 Bir dize için bir liste denetimini ekler.  
  
```  
virtual int AddItem(
    const CString& strIext,  
    DWORD_PTR dwData=0,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`strIext`  
 Bir dize başvuru.  
  
 [in]`dwData`  
 Dizesi ile ilişkili bir uygulamaya özgü 32-bit değeri. Varsayılan değer 0’dır.  
  
 [in]`iIndex`  
 Dize barındıracak konumu sıfır tabanlı dizini. Varsa `iIndex` parametredir -1, dize listesinin sonuna eklenir. Varsayılan değer -1'dir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste denetimi dize konumda sıfır tabanlı dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CVSListBox::GetItemData](#getitemdata) tarafından belirtilen değeri almaya yöntemi `dwData` parametresi. Bu değer, uygulamaya özgü tamsayı veya diğer veri gösteren bir işaretçi olabilir.  
  
##  <a name="cvslistbox"></a>CVSListBox::CVSListBox  
 Oluşturan bir `CVSListBox` nesnesi.  
  
```  
CVSListBox();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="edititem"></a>CVSListBox::EditItem  
 Liste Denetim öğesi metni düzenleme işlemi başlatır.  
  
```  
virtual BOOL EditItem(int iIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`iIndex`  
 Liste Denetim öğesi sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`düzenleme işlemi başarıyla başlatılırsa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir öğenin etiketini çift tıklatarak ya da basarak kullanıcı düzenleme işlemi başlatır **F2** veya **boşluk** anahtar öğenin odağa sahip olduğunda.  
  
##  <a name="getcount"></a>CVSListBox::GetCount  
 Bir düzenlenebilir bir liste denetimini dizelerde sayısını alır.  
  
```  
virtual int GetCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste denetiminde öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Sıfır tabanlı dizin olduğu için sayısı bir son öğenin dizini değerden daha büyük olduğunu unutmayın.  
  
##  <a name="getitemdata"></a>CVSListBox::GetItemData  
 Düzenlenebilir bir liste denetim öğesi ile ilişkilendirilen bir uygulamaya özgü 32-bit değeri alır.  
  
```  
virtual DWORD_PTR GetItemData(int iIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`iIndex`  
 Düzenlenebilir bir liste denetimini öğenin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen öğesiyle ilişkili 32-bit değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CVSListBox::SetItemData](#setitemdata) veya [CVSListBox::AddItem](#additem) 32-bit değeri liste denetim öğesi ile ilişkilendirilecek yöntemi. Bu değer, uygulamaya özgü tamsayı veya diğer veri gösteren bir işaretçi olabilir.  
  
##  <a name="getitemtext"></a>CVSListBox::GetItemText  
 Düzenlenebilir bir liste denetimini öğenin metnini alır.  
  
```  
virtual CString GetItemText(int iIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`iIndex`  
 Düzenlenebilir bir liste denetimini öğenin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) belirtilen öğenin metnini içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getlisthwnd"></a>CVSListBox::GetListHwnd  
 Tanıtıcı geçerli katıştırılmış liste görünümü denetimi döndürür.  
  
```  
virtual HWND GetListHwnd() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Katıştırılmış liste görünümü denetimi için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Destekleyen katıştırılmış liste görünümü denetimi için bir tanıtıcı almak için bu yöntemi kullanın `CVSListBox` sınıfı.  
  
##  <a name="getselitem"></a>CVSListBox::GetSelItem  
 Düzenlenebilir bir liste denetiminde seçili öğenin sıfır tabanlı dizinini alır.  
  
```  
virtual int GetSelItem() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem başarılı olursa; şu anda seçili öğenin sıfır tabanlı dizini Aksi durumda, -1.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removeitem"></a>CVSListBox::RemoveItem  
 Düzenlenebilir bir liste denetiminden öğeyi kaldırır.  
  
```  
virtual BOOL RemoveItem(int iIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`iIndex`  
 Düzenlenebilir bir liste denetimini öğenin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Belirtilen öğe kaldırılırsa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="selectitem"></a>CVSListBox::SelectItem  
 Düzenlenebilir bir liste denetimini dizisi seçer.  
  
```  
virtual BOOL SelectItem(int iItem);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`iItem`  
 Düzenlenebilir bir liste denetimini öğenin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Bu yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, belirtilen öğeyi seçer ve gerekliyse, öğe görünüme gelene.  
  
##  <a name="setitemdata"></a>CVSListBox::SetItemData  
 Bir uygulamaya özgü 32-bit değeri bir düzenlenebilir liste denetim öğesi ile ilişkilendirir.  
  
```  
virtual void SetItemData(
    int iIndex,  
    DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`iIndex`  
 Düzenlenebilir bir liste denetimini öğenin sıfır tabanlı dizini.  
  
 [in]`dwData`  
 32-bitlik bir değer. Bu değer, uygulamaya özgü tamsayı veya diğer veri gösteren bir işaretçi olabilir.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıflar](../../mfc/reference/mfc-classes.md)
