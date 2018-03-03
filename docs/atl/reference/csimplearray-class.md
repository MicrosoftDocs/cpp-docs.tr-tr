---
title: "CSimpleArray sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::Add
- ATLSIMPCOLL/ATL::CSimpleArray::Find
- ATLSIMPCOLL/ATL::CSimpleArray::GetData
- ATLSIMPCOLL/ATL::CSimpleArray::GetSize
- ATLSIMPCOLL/ATL::CSimpleArray::Remove
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleArray::SetAtIndex
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArray class
ms.assetid: ee0c9f39-b61c-4c18-bc43-4eada21dca3a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9ea081d3868c1226638d01be9505eb9d0e01ed10
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="csimplearray-class"></a>CSimpleArray sınıfı
Bu sınıf, basit bir dizi yönetme için yöntemleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T, class TEqual = CSimpleArrayEqualHelper<T>>  
class CSimpleArray
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Dizideki depolamak için veri türü.  
  
 `TEqual`  
 Eşitlik test türündeki öğeler için tanımlama bir ayırdedici nitelik nesnesi `T`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSimpleArray::CSimpleArray](#csimplearray)|Basit dizi Oluşturucusu.|  
|[CSimpleArray:: ~ CSimpleArray](#dtor)|Basit dizi yıkıcı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSimpleArray::Add](#add)|Diziye yeni bir öğe ekler.|  
|[CSimpleArray::Find](#find)|Bir öğenin dizideki bulur.|  
|[CSimpleArray::GetData](#getdata)|Dizideki depolanan veriler için bir işaretçi döndürür.|  
|[CSimpleArray::GetSize](#getsize)|Dizide saklanan öğe sayısını döndürür.|  
|[CSimpleArray::Remove](#remove)|Belirli bir öğenin array öğesinden kaldırır.|  
|[CSimpleArray::RemoveAll](#removeall)|Tüm öğeleri array öğesinden kaldırır.|  
|[CSimpleArray::RemoveAt](#removeat)|Belirtilen öğe array öğesinden kaldırır.|  
|[CSimpleArray::SetAtIndex](#setatindex)|Belirtilen öğe dizideki ayarlar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSimpleArray::operator\[\]](#operator_at)|Bir öğenin diziden alır.|  
|[CSimpleArray::operator =](#operator_eq)|Atama işleci.|  

  
## <a name="remarks"></a>Açıklamalar  
 `CSimpleArray`oluşturma ve herhangi bir türde basit bir dizi yönetme için yöntemleri sağlar `T`.  
  
 Parametre `TEqual` iki öğe türü için bir eşitlik işlevi tanımlayan bir sağlar `T`. Bir sınıf benzer oluşturarak [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md), belirli bir dizi eşitlik test davranışını değiştirmek mümkündür. Örneğin, bir dizi işaretçileri ile ilgilenirken, onu olarak eşitlik işaretçileri başvuru değerleri bağlı olarak tanımlamak yararlı olabilir. Varsayılan uygulama yararlanan **operator=()**.  
  
 Her ikisi de `CSimpleArray` ve [CSimpleMap](../../atl/reference/csimplemap-class.md) az sayıda öğesi için tasarlanmıştır. [CAtlArray](../../atl/reference/catlarray-class.md) ve [CAtlMap](../../atl/reference/catlmap-class.md) dizi öğeleri çok sayıda içerdiğinde kullanılmalıdır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsimpcoll.h  
  
## <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#86](../../atl/codesnippet/cpp/csimplearray-class_1.cpp)]  
  
##  <a name="add"></a>CSimpleArray::Add  
 Diziye yeni bir öğe ekler.  
  
```
BOOL Add(const T& t);
```  
  
### <a name="parameters"></a>Parametreler  
 *t*  
 Dizi olarak eklenecek öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe başarıyla dizisine, FALSE aksi eklenir, TRUE döndürür.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#87](../../atl/codesnippet/cpp/csimplearray-class_2.cpp)]  
  
##  <a name="csimplearray"></a>CSimpleArray::CSimpleArray  
 Dizi nesnesi Oluşturucusu.  
  
```
CSimpleArray(const CSimpleArray<T, TEqual>& src);  
CSimpleArray();
```     
  
### <a name="parameters"></a>Parametreler  
 *src*  
 Varolan bir `CSimpleArray` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni ve boş bir oluşturma veri üyeleri başlatır `CSimpleArray` nesne ya da var olan bir kopyasını `CSimpleArray` nesnesi.  
  
##  <a name="dtor"></a>CSimpleArray:: ~ CSimpleArray  
 Yok Edicisi.  
  
```
~CSimpleArray();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan tüm kaynakları serbest bırakır.  
  
##  <a name="find"></a>CSimpleArray::Find  
 Bir öğenin dizideki bulur.  
  
```
int Find(const T& t) const;
```  
  
### <a name="parameters"></a>Parametreler  
 *t*  
 Aranacak öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğenin bulunamaması durumunda bulunan öğe veya -1 dizinini döndürür.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#88](../../atl/codesnippet/cpp/csimplearray-class_3.cpp)]  
  
##  <a name="getdata"></a>CSimpleArray::GetData  
 Dizideki depolanan veriler için bir işaretçi döndürür.  
  
```
T* GetData() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizideki verileri için bir işaretçi döndürür.  
  
##  <a name="getsize"></a>CSimpleArray::GetSize  
 Dizide saklanan öğe sayısını döndürür.  
  
```
int GetSize() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizide saklanan öğe sayısını döndürür.  
  
##  <a name="operator_at"></a>CSimpleArray::operator\[\]  
 Bir öğenin diziden alır.  
  
```
T& operator[](int nindex);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Öğenin dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından başvurulan dizi öğeyi döndürür `nIndex`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#89](../../atl/codesnippet/cpp/csimplearray-class_4.cpp)]  
  
##  <a name="operator_eq"></a>CSimpleArray::operator =  
 Atama işleci.  
  
```
CSimpleArray<T, TEqual>
& operator=(
    const CSimpleArray<T, TEqual>& src);
```  
  
### <a name="parameters"></a>Parametreler  
 *src*  
 Kopyalamak için dizisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi güncelleştirilmiş döndüren `CSimpleArray` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm öğeleri kopyalar `CSimpleArray` tarafından başvurulan nesne *src* geçerli dizi nesnesine varolan tüm verileri değiştirme.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#90](../../atl/codesnippet/cpp/csimplearray-class_5.cpp)]  
  
##  <a name="remove"></a>CSimpleArray::Remove  
 Belirli bir öğenin array öğesinden kaldırır.  
  
```
BOOL Remove(const T& t);
```  
  
### <a name="parameters"></a>Parametreler  
 *t*  
 Array öğesinden kaldırılacak öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe bulundu ve kaldırıldı, FALSE değilse TRUE döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir öğe kaldırıldığında, dizideki kalan öğelerin boş alanı dolduracak şekilde numaralandırılır.  
  
##  <a name="removeall"></a>CSimpleArray::RemoveAll  
 Tüm öğeleri array öğesinden kaldırır.  
  
```
void RemoveAll();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şu anda dizisinde depolanan tüm öğeleri kaldırır.  
  
##  <a name="removeat"></a>CSimpleArray::RemoveAt  
 Belirtilen öğe array öğesinden kaldırır.  
  
```
BOOL RemoveAtint nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Kaldırılacak öğenin işaret eden dizin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE öğesi, varsa kaldırılan, dizini geçersizdi ise FALSE değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir öğe kaldırıldığında, dizideki kalan öğelerin boş alanı dolduracak şekilde numaralandırılır.  
  
##  <a name="setatindex"></a>CSimpleArray::SetAtIndex  
 Belirtilen öğe dizideki ayarlayın.  
  
```
BOOL SetAtIndex(
    int nIndex,
    const T& t);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Değiştirilecek öğenin dizini.  
  
 *t*  
 Belirtilen öğe atanacak değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE başarılı olduğunda, yanlış dizini geçerli değil, döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
