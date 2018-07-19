---
title: CSimpleArray sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2ef8a6a9b803cb7e1828537027bbf09b2ffd2067
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37881639"
---
# <a name="csimplearray-class"></a>CSimpleArray sınıfı
Bu sınıf, bir Basit dizi yönetmek için yöntemler sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T, class TEqual = CSimpleArrayEqualHelper<T>>  
class CSimpleArray
```  
  
#### <a name="parameters"></a>Parametreler  
 *T*  
 Dizide saklamak için veri türü.  
  
 *TEqual*  
 Türü öğeler için eşitlik testi tanımlamak bir nitelik nesnesi *T*.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSimpleArray::CSimpleArray](#csimplearray)|Basit dizi için oluşturucu.|  
|[CSimpleArray:: ~ CSimpleArray](#dtor)|Basit dizi yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSimpleArray::Add](#add)|Diziye yeni bir öğe ekler.|  
|[CSimpleArray::Find](#find)|Dizide bir öğe bulur.|  
|[CSimpleArray::GetData](#getdata)|Dizide depolanan veriler için bir işaretçi döndürür.|  
|[CSimpleArray::GetSize](#getsize)|Dizide depolanan öğelerin sayısını döndürür.|  
|[CSimpleArray::Remove](#remove)|Diziden belirli bir öğeyi kaldırır.|  
|[CSimpleArray::RemoveAll](#removeall)|Dizinin tüm öğeleri kaldırır.|  
|[CSimpleArray::RemoveAt](#removeat)|Belirtilen öğe diziden kaldırır.|  
|[CSimpleArray::SetAtIndex](#setatindex)|Belirtilen öğe dizideki ayarlar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSimpleArray::operator\[\]](#operator_at)|Öğe diziden alır.|  
|[CSimpleArray::operator =](#operator_eq)|Atama işleci.|  

  
## <a name="remarks"></a>Açıklamalar  
 `CSimpleArray` oluşturma ve herhangi bir türü bir Basit dizi yönetmek için yöntemler sağlar `T`.  
  
 Parametre `TEqual` tanımlamanın iki türü öğeler için bir eşitlik işlevi sağlar `T`. Bir sınıf benzer oluşturarak [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md), verilen herhangi bir dizi için eşitlik testi davranışını değiştirmek mümkündür. Örneğin, bir işaretçiler dizisi ile ilgilenirken, bu değerlerin işaretçileri başvuran bağlı olarak bir eşitlik tanımlamak yararlı olabilir. Varsayılan uygulama yararlanan **operator=()**.  
  
 Her ikisi de `CSimpleArray` ve [CSimpleMap](../../atl/reference/csimplemap-class.md) küçük bir dizi öğe için tasarlanmıştır. [CAtlArray](../../atl/reference/catlarray-class.md) ve [CAtlMap](../../atl/reference/catlmap-class.md) dizi çok sayıda öğe içerdiğinde kullanılmalıdır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsimpcoll.h  
  
## <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#86](../../atl/codesnippet/cpp/csimplearray-class_1.cpp)]  
  
##  <a name="add"></a>  CSimpleArray::Add  
 Diziye yeni bir öğe ekler.  
  
```
BOOL Add(const T& t);
```  
  
### <a name="parameters"></a>Parametreler  
 *T*  
 Diziye eklenecek öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe başarıyla diziye FALSE Aksi durumda eklenir, TRUE döndürür.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#87](../../atl/codesnippet/cpp/csimplearray-class_2.cpp)]  
  
##  <a name="csimplearray"></a>  CSimpleArray::CSimpleArray  
 Dizi nesnesi için oluşturucu.  
  
```
CSimpleArray(const CSimpleArray<T, TEqual>& src);  
CSimpleArray();
```     
  
### <a name="parameters"></a>Parametreler  
 *src*  
 Varolan bir `CSimpleArray` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni ve boş bir oluşturma, veri üyeleri başlatır `CSimpleArray` nesne veya varolan bir kopyasını `CSimpleArray` nesne.  
  
##  <a name="dtor"></a>  CSimpleArray:: ~ CSimpleArray  
 Yıkıcı.  
  
```
~CSimpleArray();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan tüm kaynakları serbest bırakır.  
  
##  <a name="find"></a>  CSimpleArray::Find  
 Dizide bir öğe bulur.  
  
```
int Find(const T& t) const;
```  
  
### <a name="parameters"></a>Parametreler  
 *T*  
 Aranacak öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğenin bulunamaması durumunda bulunan öğe veya -1 dizinini döndürür.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#88](../../atl/codesnippet/cpp/csimplearray-class_3.cpp)]  
  
##  <a name="getdata"></a>  CSimpleArray::GetData  
 Dizide depolanan veriler için bir işaretçi döndürür.  
  
```
T* GetData() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizi içindeki verileri için bir işaretçi döndürür.  
  
##  <a name="getsize"></a>  CSimpleArray::GetSize  
 Dizide depolanan öğelerin sayısını döndürür.  
  
```
int GetSize() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizide depolanan öğelerin sayısını döndürür.  
  
##  <a name="operator_at"></a>  CSimpleArray::operator \[\]  
 Öğe diziden alır.  
  
```
T& operator[](int nindex);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Öğenin dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından başvurulan dizinin bir öğesine döndürür *nIndex*.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#89](../../atl/codesnippet/cpp/csimplearray-class_4.cpp)]  
  
##  <a name="operator_eq"></a>  CSimpleArray::operator =  
 Atama işleci.  
  
```
CSimpleArray<T, TEqual>
& operator=(
    const CSimpleArray<T, TEqual>& src);
```  
  
### <a name="parameters"></a>Parametreler  
 *src*  
 Kopyalamak için dizi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş bir işaretçi döndürür `CSimpleArray` nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm öğeleri kopyalar `CSimpleArray` tarafından başvurulan nesne *src* geçerli dizi nesnesine tüm mevcut veriler değiştiriliyor.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#90](../../atl/codesnippet/cpp/csimplearray-class_5.cpp)]  
  
##  <a name="remove"></a>  CSimpleArray::Remove  
 Diziden belirli bir öğeyi kaldırır.  
  
```
BOOL Remove(const T& t);
```  
  
### <a name="parameters"></a>Parametreler  
 *T*  
 Diziden kaldırılacak öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe Aksi halde bulunan ve kaldırılmış, FALSE ise TRUE döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir öğe kaldırıldığında, dizinin kalan öğeleri boş alanı dolduracak şekilde numaralandırılır.  
  
##  <a name="removeall"></a>  CSimpleArray::RemoveAll  
 Dizinin tüm öğeleri kaldırır.  
  
```
void RemoveAll();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şu anda dizide depolanan tüm öğeleri kaldırır.  
  
##  <a name="removeat"></a>  CSimpleArray::RemoveAt  
 Belirtilen öğe diziden kaldırır.  
  
```
BOOL RemoveAtint nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Kaldırmak için öğeyi işaret eden dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğesi, varsa kaldırıldı, yanlış dizini geçersizdi TRUE döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir öğe kaldırıldığında, dizinin kalan öğeleri boş alanı dolduracak şekilde numaralandırılır.  
  
##  <a name="setatindex"></a>  CSimpleArray::SetAtIndex  
 Belirtilen öğe dizideki ayarlayın.  
  
```
BOOL SetAtIndex(
    int nIndex,
    const T& t);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Değiştirilecek öğenin dizini.  
  
 *T*  
 Belirtilen öğe için atanacak değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 DOĞRU başarılı, yanlış dizini geçerli değil, döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
