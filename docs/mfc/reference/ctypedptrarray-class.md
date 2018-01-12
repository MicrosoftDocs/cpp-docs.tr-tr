---
title: "CTypedPtrArray sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTypedPtrArray
- AFXTEMPL/CTypedPtrArray
- AFXTEMPL/CTypedPtrArray::Add
- AFXTEMPL/CTypedPtrArray::Append
- AFXTEMPL/CTypedPtrArray::Copy
- AFXTEMPL/CTypedPtrArray::ElementAt
- AFXTEMPL/CTypedPtrArray::GetAt
- AFXTEMPL/CTypedPtrArray::InsertAt
- AFXTEMPL/CTypedPtrArray::SetAt
- AFXTEMPL/CTypedPtrArray::SetAtGrow
dev_langs: C++
helpviewer_keywords:
- CTypedPtrArray [MFC], Add
- CTypedPtrArray [MFC], Append
- CTypedPtrArray [MFC], Copy
- CTypedPtrArray [MFC], ElementAt
- CTypedPtrArray [MFC], GetAt
- CTypedPtrArray [MFC], InsertAt
- CTypedPtrArray [MFC], SetAt
- CTypedPtrArray [MFC], SetAtGrow
ms.assetid: e3ecdf1a-a889-4156-92dd-ddbd36ccd919
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6e08749341bd7865c89e397e36aeff3a6ccc0d71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ctypedptrarray-class"></a>CTypedPtrArray sınıfı
Tür kullanımı uyumlu "sarmalayıcı" sınıfının nesneleri için sağlar `CPtrArray` veya `CObArray`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<class BASE_CLASS, class TYPE>  
class CTypedPtrArray : public BASE_CLASS  
```  
  
#### <a name="parameters"></a>Parametreler  
 `BASE_CLASS`  
 Yazılan işaretçi dizi sınıfın temel sınıf; array sınıfı olmalıdır ( `CObArray` veya `CPtrArray`).  
  
 `TYPE`  
 Taban sınıfı dizisinde depolanan öğelerin türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTypedPtrArray::Add](#add)|Yeni bir öğesi bir dizi sonuna ekler. Gerekirse, dizi büyümesi|  
|[CTypedPtrArray::Append](#append)|Bir dizinin içeriğini başka sonuna ekler. Gerekirse, dizi büyümesi|  
|[CTypedPtrArray::Copy](#copy)|Başka bir dizi diziye kopyalar; dizi gerekirse artar.|  
|[CTypedPtrArray::ElementAt](#elementat)|Dizi öğesi işaretçinin geçici bir başvuru döndürür.|  
|[CTypedPtrArray::GetAt](#getat)|Belirtilen dizindeki değeri döndürür.|  
|[CTypedPtrArray::InsertAt](#insertat)|Bir öğenin (veya başka bir dizinin tüm öğeleri) belirtilen bir dizinde ekler.|  
|[CTypedPtrArray::SetAt](#setat)|Belirli bir dizine için değeri ayarlar; dizi büyümeye izin verilmiyor.|  
|[CTypedPtrArray::SetAtGrow](#setatgrow)|Belirli bir dizine için değeri ayarlar; dizi gerekirse artar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTypedPtrArray::operator]](#operator_at)|Belirtilen dizindeki öğeyi alır veya ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullandığınızda `CTypedPtrArray` yerine `CPtrArray` veya `CObArray`, C++ tür denetleme olanağı eşleşmeyen işaretçi türlerine göre neden olduğu hata ortadan kaldırmanıza yardımcı olur.  
  
 Ayrıca, `CTypedPtrArray` sarmalayıcı kullandıysanız, gerekli olacak atama çoğunu gerçekleştirir `CObArray` veya `CPtrArray`.  
  
 Çünkü tüm `CTypedPtrArray` işlevler satır içi, bu şablonu kullanımını boyutunu veya kodunuzu hızına önemli ölçüde etkilemez.  
  
 Kullanma hakkında daha fazla bilgi için `CTypedPtrArray`, makalelerine bakın [koleksiyonları](../../mfc/collections.md) ve [şablona dayalı sınıflar](../../mfc/template-based-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `BASE_CLASS`  
  
 `CTypedPtrArray`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxtempl.h  
  
##  <a name="add"></a>CTypedPtrArray::Add  
 Bu üye işlevi çağırır `BASE_CLASS` **:: Ekle**.  
  
```  
INT_PTR Add(TYPE newElement);
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Dizi olarak eklenecek öğenin türünü belirten bir şablon parametre.  
  
 `newElement`  
 Bu diziye eklenecek öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eklenen öğenin dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha ayrıntılı açıklamalar için bkz: [CObArray::Add](../../mfc/reference/cobarray-class.md#add).  
  
##  <a name="append"></a>CTypedPtrArray::Append  
 Bu üye işlevi çağırır `BASE_CLASS` **:: Append**.  
  
```  
INT_PTR Append(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```  
  
### <a name="parameters"></a>Parametreler  
 `BASE_CLASS`  
 Yazılan işaretçi dizi sınıfın temel sınıf; array sınıfı olmalıdır ( [CObArray](../../mfc/reference/cobarray-class.md) veya [CPtrArray](../../mfc/reference/cptrarray-class.md)).  
  
 *TÜRÜ*  
 Taban sınıfı dizisinde depolanan öğelerin türü.  
  
 *src*  
 Kaynağı için bir dizi eklenecek öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk eklenmiş öğenin dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha ayrıntılı açıklamalar için bkz: [CObArray::Append](../../mfc/reference/cobarray-class.md#append).  
  
##  <a name="copy"></a>CTypedPtrArray::Copy  
 Bu üye işlevi çağırır `BASE_CLASS` **:: kopyalama**.  
  
```  
void Copy(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```  
  
### <a name="parameters"></a>Parametreler  
 `BASE_CLASS`  
 Yazılan işaretçi dizi sınıfın temel sınıf; array sınıfı olmalıdır ( [CObArray](../../mfc/reference/cobarray-class.md) veya [CPtrArray](../../mfc/reference/cptrarray-class.md)).  
  
 *TÜRÜ*  
 Taban sınıfı dizisinde depolanan öğelerin türü.  
  
 *src*  
 Kaynak öğelerin bir diziye kopyalar.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha ayrıntılı açıklamalar için bkz: [CObArray::Copy](../../mfc/reference/cobarray-class.md#copy).  
  
##  <a name="elementat"></a>CTypedPtrArray::ElementAt  
 Bu satır içi işlev çağrılarını `BASE_CLASS` **:: ElementAt**.  
  
```  
TYPE& ElementAt(INT_PTR nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Bu dizide saklanan öğelerin türünü belirten bir şablon parametre.  
  
 `nIndex`  
 Büyük veya 0 değerine eşit bir tamsayı dizini ve tarafından döndürülen değer eşit veya daha az `BASE_CLASS` **:: GetUpperBound**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğesi tarafından belirtilen konumda geçici bir başvuru `nIndex`. Bu şablon parametresi tarafından belirtilen türde öğedir *türü*.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha ayrıntılı açıklamalar için bkz: [CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat).  
  
##  <a name="getat"></a>CTypedPtrArray::GetAt  
 Bu satır içi işlev çağrılarını `BASE_CLASS` **:: GetAt**.  
  
```  
TYPE GetAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Dizide saklanan öğelerin türünü belirten bir şablon parametre.  
  
 `nIndex`  
 Büyük veya 0 değerine eşit bir tamsayı dizini ve tarafından döndürülen değer eşit veya daha az `BASE_CLASS` **:: GetUpperBound**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğesi tarafından belirtilen konumda bir kopyasını `nIndex`. Bu şablon parametresi tarafından belirtilen türde öğedir *türü*.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha ayrıntılı açıklamalar için bkz: [CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)  
  
##  <a name="insertat"></a>CTypedPtrArray::InsertAt  
 Bu üye işlevi çağırır `BASE_CLASS` **:: InsertAt**.  
  
```  
void InsertAt(
    INT_PTR nIndex,  
    TYPE newElement,  
    INT_PTR nCount = 1);

 
void InsertAt(
    INT_PTR nStartIndex,  
    CTypedPtrArray<BASE_CLASS, TYPE>* pNewArray);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Tarafından döndürülen değeri,'den büyük bir tamsayı dizini [CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound).  
  
 *TÜRÜ*  
 Taban sınıfı dizisinde depolanan öğelerin türü.  
  
 `newElement`  
 Bu dizide yerleştirilecek nesne işaretçisi. A `newElement` değerinin **NULL** izin verilir.  
  
 `nCount`  
 Bu öğe olmalıdır sayısı (varsayılan 1) ekledi.  
  
 `nStartIndex`  
 Tarafından döndürülen değeri,'den büyük bir tamsayı dizini `CObArray::GetUpperBound`.  
  
 `BASE_CLASS`  
 Yazılan işaretçi dizi sınıfın temel sınıf; array sınıfı olmalıdır ( [CObArray](../../mfc/reference/cobarray-class.md) veya [CPtrArray](../../mfc/reference/cptrarray-class.md)).  
  
 `pNewArray`  
 Bu diziye eklenecek öğeleri içeren başka bir dizi.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha ayrıntılı açıklamalar için bkz: [CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat).  
  
##  <a name="operator_at"></a>CTypedPtrArray::operator]  
 Bu satır içi işleçler çağrısı `BASE_CLASS` **:: işleci []**.  
  
```  
TYPE& operator[ ](int_ptr nindex);  
TYPE operator[ ](int_ptr nindex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Dizide saklanan öğelerin türünü belirten bir şablon parametre.  
  
 `nIndex`  
 Büyük veya 0 değerine eşit bir tamsayı dizini ve tarafından döndürülen değer eşit veya daha az `BASE_CLASS` **:: GetUpperBound**.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk işleci adlı olmayan diziler için **const**, sağ (r) veya Atama ifadesinin sol (l-değeri) üzerinde kullanılabilir. İkincisi, çağrılan **const** dizileri, yalnızca sağdaki kullanılabilir.  
  
 Alt simge (ya da sol veya sağ tarafında Atama ifadesinin) sınırların dışında olup olmadığını kitaplığının hata ayıklama sürümü onaylar.  
  
##  <a name="setat"></a>CTypedPtrArray::SetAt  
 Bu üye işlevi çağırır `BASE_CLASS` **:: SetAt**.  
  
```  
void SetAt(
    INT_PTR nIndex,  
    TYPE ptr);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Büyük veya 0 değerine eşit bir tamsayı dizini ve tarafından döndürülen değer eşit veya daha az [CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound).  
  
 *TÜRÜ*  
 Taban sınıfı dizisinde depolanan öğelerin türü.  
  
 *ptr*  
 Dizide nIndex eklenecek öğe için bir işaretçi. Bir NULL değerine izin verilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha ayrıntılı açıklamalar için bkz: [CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat).  
  
##  <a name="setatgrow"></a>CTypedPtrArray::SetAtGrow  
 Bu üye işlevi çağırır `BASE_CLASS` **:: SetAtGrow**.  
  
```  
void SetAtGrow(
    INT_PTR nIndex,  
    TYPE newElement);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Büyük veya 0 değerine eşit bir tamsayı dizini.  
  
 *TÜRÜ*  
 Taban sınıfı dizisinde depolanan öğelerin türü.  
  
 `newElement`  
 Bu diziye eklenecek nesne işaretçisi. A **NULL** değerine izin verilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha ayrıntılı açıklamalar için bkz: [CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek Topla](../../visual-cpp-samples.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CPtrArray sınıfı](../../mfc/reference/cptrarray-class.md)   
 [CObArray Sınıfı](../../mfc/reference/cobarray-class.md)
