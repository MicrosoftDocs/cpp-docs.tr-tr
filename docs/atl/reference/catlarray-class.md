---
title: "CAtlArray sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlArray
- ATLCOLL/ATL::CAtlArray
- ATLCOLL/ATL::Add
- ATLCOLL/ATL::Append
- ATLCOLL/ATL::AssertValid
- ATLCOLL/ATL::Copy
- ATLCOLL/ATL::FreeExtra
- ATLCOLL/ATL::GetAt
- ATLCOLL/ATL::GetCount
- ATLCOLL/ATL::GetData
- ATLCOLL/ATL::InsertArrayAt
- ATLCOLL/ATL::InsertAt
- ATLCOLL/ATL::IsEmpty
- ATLCOLL/ATL::RemoveAll
- ATLCOLL/ATL::RemoveAt
- ATLCOLL/ATL::SetAt
- ATLCOLL/ATL::SetAtGrow
- ATLCOLL/ATL::SetCount
- ATLCOLL/ATL::INARGTYPE
- ATLCOLL/ATL::OUTARGTYPE
dev_langs:
- C++
helpviewer_keywords:
- CAtlArray class
ms.assetid: 0b503aa8-2357-40af-a326-6654bf1da098
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ffebf8289b7c1eb5ccaae5a6b6a5f2a3f939cbb9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="catlarray-class"></a>CAtlArray sınıfı
Bu sınıf, bir dizi nesnesi uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename E, class ETraits = CElementTraits<E>>
class CAtlArray
```  
  
#### <a name="parameters"></a>Parametreler  
 *E*  
 Dizideki depolanması için veri türü.  
  
 *ETraits*  
 Kopyalama veya öğeleri taşıma için kullanılan kod.  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[Ekleme](#add)|Dizi nesnesi için bir öğe eklemek için bu yöntemi çağırın.|  
|[Ekleme](#append)|Bir dizinin içeriğini başka sonuna eklemek için bu yöntemi çağırın.|  
|[AssertValid](#assertvalid)|Dizi nesnesinin geçerli olduğundan emin olmak için bu yöntemi çağırın.|  
|[CAtlArray](#catlarray)|Oluşturucu.|  
|[~ CAtlArray](#dtor)|Yok Edicisi.|  
|[Kopyalama](#copy)|Bir dizinin öğeleri diğerine kopyalamak için bu yöntemi çağırın.|  
|[FreeExtra](#freeextra)|Array öğesinden boş tüm öğeleri kaldırmak için bu yöntemi çağırın.|  
|[GetAt](#getat)|Tek bir öğe dizi nesnesinden almak için bu yöntemi çağırın.|  
|[GetCount](#getcount)|Dizide saklanan öğe sayısını döndürmek için bu yöntemi çağırın.|  
|[GetData](#getdata)|Dizinin ilk öğe için bir işaretçi döndürmek için bu yöntemi çağırın.|  
|[InsertArrayAt](#insertarrayat)|Bir dizi diğerine eklemek için bu yöntemi çağırın.|  
|[InsertAt](#insertat)|Dizi nesnesi yeni bir öğenin (veya birden çok kopya, bir öğenin) eklemek için bu yöntemi çağırın.|  
|[IsEmpty](#isempty)|Dizi boş ise test etmek için bu yöntemi çağırın.|  
|[RemoveAll](#removeall)|Dizi nesneden tüm öğeleri kaldırmak için bu yöntemi çağırın.|  
|[RemoveAt](#removeat)|Bir veya daha fazla öğe diziden kaldırmak için bu yöntemi çağırın.|  
|[SetAt](#setat)|Bir öğenin değeri dizi nesnesinin ayarlamak için bu yöntemi çağırın.|  
|[SetAtGrow](#setatgrow)|Bir dizi gerekli olarak genişletme dizi nesnesi, bir öğenin değerini ayarlamak için bu yöntemi çağırın.|  
|[SetCount](#setcount)|Dizi nesnesi boyutunu ayarlamak için bu yöntemi çağırın.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[operator &#91; &#93;](#operator_at)|Bir öğenin bir başvuru dizideki döndürmek için bu işleci çağırın.|  

  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[INARGTYPE](#inargtype)|Diziye öğe eklemek için kullanılacak veri türü.|  
|[OUTARGTYPE](#outargtype)|Array öğesinden öğeleri almak için kullanılacak veri türü.|  
  
## <a name="remarks"></a>Açıklamalar  
 **CAtlArray** oluşturmak ve kullanıcı tanımlı bir tür öğelerinin bir dizisini yönetme için yöntemleri sağlar. Benzer ancak standart C dizi **CAtlArray** nesnesi, dinamik olarak küçültmek ve gerektikçe büyütün. Dizi dizini her zaman 0 konumunda başlar ve üst sınırı sabit veya yeni öğeler eklendikçe genişletmek için izin verilen.  
  
 Az sayıda öğesi, ATL sınıfı ile diziler için [CSimpleArray](../../atl/reference/csimplearray-class.md) kullanılabilir.  
  
 **CAtlArray** MFC'nin için yakından ilgili **CArray** sınıfı ve MFC projesinde barındırabilir serileştirme desteği olmadan çalışır.  
  
 Daha fazla bilgi için bkz: [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="add"></a>CAtlArray::Add  
 Dizi nesnesi için bir öğe eklemek için bu yöntemi çağırın.  
  
```
size_t Add(INARGTYPE element);
size_t Add();
```  
  
### <a name="parameters"></a>Parametreler  
 `element`  
 Dizi olarak eklenecek öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eklenen öğenin dizinini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni öğe dizinin sonuna eklenir. Boş bir öğe eklenen sağlanan herhangi bir öğe varsa; diğer bir deyişle, gerçek bir öğe eklendi ancak gibi dizi boyutu artar. İşlem başarısız olursa [AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow) E_OUTOFMEMORY bağımsız değişken ile çağrıldı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#1](../../atl/codesnippet/cpp/catlarray-class_1.cpp)]  
  
##  <a name="append"></a>CAtlArray::Append  
 Bir dizinin içeriğini başka sonuna eklemek için bu yöntemi çağırın.  
  
```
size_t Append(const CAtlArray<E, ETraits>& aSrc);
```  
  
### <a name="parameters"></a>Parametreler  
 `aSrc`  
 Eklenecek dizisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk eklenmiş öğenin dizinini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Sağlanan dizideki öğeler mevcut dizinin sonuna eklenir. Gerekirse, yeni öğeleri yerleştirmek için bellek tahsis edilir.  
  
 Diziler aynı türde olması gerekir ve kendisine bir dizi eklemek mümkün değildir.  
  
 Hata ayıklama derlemelerinde bir ATLASSERT gerçekleştirilecektir `CAtlArray` bağımsız değişkeni geçerli bir dizi değil veya `aSrc` de aynı nesneye başvuruyor. Yayın derlemelerde geçersiz bağımsız değişkenler için beklenmeyen davranışlara neden olabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#2](../../atl/codesnippet/cpp/catlarray-class_2.cpp)]  
  
##  <a name="assertvalid"></a>CAtlArray::AssertValid  
 Dizi nesnesinin geçerli olduğundan emin olmak için bu yöntemi çağırın.  
  
```
void AssertValid() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dizi nesnesi geçerli değilse `ATLASSERT` bir onaylama işlemi özel durum oluşturacak. Bu yöntem yalnızca _DEBUG tanımlıysa kullanılabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#3](../../atl/codesnippet/cpp/catlarray-class_3.cpp)]  
  
##  <a name="catlarray"></a>CAtlArray::CAtlArray  
 Oluşturucu.  
  
```
CAtlArray() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dizi nesnesi başlatır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#4](../../atl/codesnippet/cpp/catlarray-class_4.cpp)]  
  
##  <a name="dtor"></a>CAtlArray:: ~ CAtlArray  
 Yok Edicisi.  
  
```
~CAtlArray() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dizi nesnesi tarafından kullanılan tüm kaynakları serbest bırakır.  
  
##  <a name="copy"></a>CAtlArray::Copy  
 Bir dizinin öğeleri diğerine kopyalamak için bu yöntemi çağırın.  
  
```
void Copy(const CAtlArray<E, ETraits>& aSrc);
```  
  
### <a name="parameters"></a>Parametreler  
 `aSrc`  
 Öğeleri bir diziye kopyalamak için kaynağı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir dizinin öğeleri başka bir dizi öğelerle üzerine yazmak için bu yöntemi çağırın. Gerekirse, yeni öğeleri yerleştirmek için bellek tahsis edilir. Dizi öğelerini kendisine kopyalama mümkün değil.  
  
 Mevcut dizinin içeriğini tutulacak kullanırsanız [CAtlArray::Append](#append) yerine.  
  
 Hata ayıklama derlemelerinde bir ATLASSERT gerçekleştirilecektir varolan `CAtlArray` nesnesi geçerli değil veya `aSrc` de aynı nesneye başvuruyor. Yayın derlemelerde geçersiz bağımsız değişkenler için beklenmeyen davranışlara neden olabilir.  
  
> [!NOTE]
> `CAtlArray::Copy`ile oluşturulan öğeleri oluşan diziler desteklemiyor [CAutoPtr](../../atl/reference/cautoptr-class.md) sınıfı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#5](../../atl/codesnippet/cpp/catlarray-class_5.cpp)]  
  
##  <a name="freeextra"></a>CAtlArray::FreeExtra  
 Array öğesinden boş tüm öğeleri kaldırmak için bu yöntemi çağırın.  
  
```
void FreeExtra() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Herhangi bir boş öğe kaldırılır, ancak dizi üst sınırının ve boyutu değişmeden kalır.  
  
 Hata ayıklama derlemelerinde, CAtlArray nesnesi geçerli değil veya dizi en büyük boyutuna aşılmasına neden olacak bir ATLASSERT gerçekleştirilecektir.  
  
##  <a name="getat"></a>CAtlArray::GetAt  
 Çağrı için bu yöntem tek bir öğe dizi nesnesinden alır.  
  
```
const E& GetAt(size_t iElement) const throw();
E& GetAt(size_t iElement) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `iElement`  
 Dizin değeri döndürmek için dizi öğesinin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gerekli dizi öğesi için bir başvuru döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata ayıklama derlemelerinde bir ATLASSERT gerçekleştirilecektir `iElement` dizideki öğelerin sayısını aşıyor. Yayın derlemelerde geçersiz bağımsız değişken için beklenmeyen davranışlara neden olabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#6](../../atl/codesnippet/cpp/catlarray-class_6.cpp)]  
  
##  <a name="getcount"></a>CAtlArray::GetCount  
 Dizide saklanan öğe sayısını döndürmek için bu yöntemi çağırın.  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizide saklanan öğe sayısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Dizinin ilk öğe 0 konumunda olduğundan, döndürülen değer tarafından `GetCount` her zaman 1'den büyük dizin büyüktür.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlArray::GetAt](#getat).  
  
##  <a name="getdata"></a>CAtlArray::GetData  
 Dizinin ilk öğe için bir işaretçi döndürmek için bu yöntemi çağırın.  
  
```
E* GetData() throw();
const E* GetData() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizideki ilk öğe depolamak bellek konumuna bir işaretçi döndürür. Öğe varsa, null değeri döndürülür.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#7](../../atl/codesnippet/cpp/catlarray-class_7.cpp)]  
  
##  <a name="inargtype"></a>CAtlArray::INARGTYPE  
 Diziye öğe eklemek için kullanılacak veri türü.  
  
```
typedef ETraits::INARGTYPE INARGTYPE;
```  
  
##  <a name="insertarrayat"></a>CAtlArray::InsertArrayAt  
 Bir dizi diğerine eklemek için bu yöntemi çağırın.  
  
```
void InsertArrayAt(size_t iStart, const CAtlArray<E, ETraits>* paNew);
```  
  
### <a name="parameters"></a>Parametreler  
 `iStart`  
 Dizi eklenecek dizini.  
  
 `paNew`  
 Eklenecek dizisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Dizi öğeleri `paNew` öğede başlayarak, bir dizi nesnesi kopyalanır `iStart`. Varolan dizi öğelerinin üzerine yazılmasını engellemek için taşınır.  
  
 Hata ayıklama derlemelerinde bir ATLASSERT gerçekleştirilecektir `CAtlArray` nesnesi geçerli değil veya `paNew` işaretçidir NULL veya geçersiz.  
  
> [!NOTE]
> `CAtlArray::InsertArrayAt`ile oluşturulan öğeleri oluşan diziler desteklemiyor [CAutoPtr](../../atl/reference/cautoptr-class.md) sınıfı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#8](../../atl/codesnippet/cpp/catlarray-class_8.cpp)]  
  
##  <a name="insertat"></a>CAtlArray::InsertAt  
 Dizi nesnesi yeni bir öğenin (veya birden çok kopya, bir öğenin) eklemek için bu yöntemi çağırın.  
  
```
void InsertAt(size_t iElement, INARGTYPE element, size_t nCount = 1);
```  
  
### <a name="parameters"></a>Parametreler  
 `iElement`  
 Veya birden çok öğe eklenecek nerede dizini.  
  
 `element`  
 Değerini veya birden çok eklenecek öğe.  
  
 `nCount`  
 Eklenecek öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir veya daha fazla öğe dizinden başlayarak bir diziye ekler `iElement`. Varolan öğeleri üzerine yazılmasını engellemek için taşınır.  
  
 Hata ayıklama derlemelerinde bir ATLASSERT gerçekleştirilecektir `CAtlArray` nesnesi geçersiz, sıfır eklenecek öğe sayısını olduğundan veya öğeleri toplam sayısı içerecek şekilde dizi için çok büyük. Perakende derlemelerde geçersiz parametreleri geçirme öngörülemeyen sonuçlara neden olabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#9](../../atl/codesnippet/cpp/catlarray-class_9.cpp)]  
  
##  <a name="isempty"></a>CAtlArray::IsEmpty  
 Dizi boş ise test etmek için bu yöntemi çağırın.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizi yanlış Aksi halde boş ise, true döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Dizi öğe içeriyorsa, boş olarak kabul edilir. Dizi boş öğeleri içeriyorsa bile, bu nedenle, bu boş değil.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#10](../../atl/codesnippet/cpp/catlarray-class_10.cpp)]  
  
##  <a name="operator_at"></a>CAtlArray::operator]  
 Bir öğenin bir başvuru dizideki döndürmek için bu işleci çağırın.  
  
```
E& operator[](size_t ielement) throw();
const E& operator[](size_t ielement) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `iElement`  
 Dizin değeri döndürmek için dizi öğesinin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gerekli dizi öğesi için bir başvuru döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Benzer bir işlevi gerçekleştiren [CAtlArray::GetAt](#getat). MFC sınıf aksine [CArray](../../mfc/reference/carray-class.md), bu işleci yerine kullanılamaz [CAtlArray::SetAt](#setat).  
  
 Hata ayıklama derlemelerinde bir ATLASSERT gerçekleştirilecektir `iElement` dizideki öğeler toplam sayısını aşıyor. Perakende derlemelerde geçersiz bir parametre öngörülemeyen sonuçlara neden olabilir.  
  
##  <a name="outargtype"></a>CAtlArray::OUTARGTYPE  
 Array öğesinden öğeleri almak için kullanılacak veri türü.  
  
```
typedef ETraits::OUTARGTYPE OUTARGTYPE;
```  
  
##  <a name="removeall"></a>CAtlArray::RemoveAll  
 Dizi nesneden tüm öğeleri kaldırmak için bu yöntemi çağırın.  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm öğeleri dizisi nesnesinden kaldırır.  
  
 Bu yöntemi çağırır [CAtlArray::SetCount](#setcount) dizi yeniden boyutlandırmak için ve daha sonra ayrılan belleği serbest bırakır.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlArray::IsEmpty](#isempty).  
  
##  <a name="removeat"></a>CAtlArray::RemoveAt  
 Bir veya daha fazla öğe diziden kaldırmak için bu yöntemi çağırın.  
  
```
void RemoveAt(size_t iElement, size_t nCount = 1);
```  
  
### <a name="parameters"></a>Parametreler  
 `iElement`  
 Kaldırmak için ilk öğenin dizini.  
  
 `nCount`  
 Kaldırılacak öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir veya daha fazla öğe array öğesinden kaldırır. Kalan öğeler gölgeye. Üst sınır düşülür ancak bellek yapılan bir çağrı kadar serbest değil [CAtlArray::FreeExtra](#freeextra) yapılır.  
  
 Hata ayıklama derlemelerinde bir ATLASSERT gerçekleştirilecektir `CAtlArray` nesnesi geçerli değil veya toplam `iElement` ve `nCount` dizideki öğeler toplam sayısını aşıyor. Perakende derlemelerde geçersiz parametreler öngörülemeyen sonuçlara neden olabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#11](../../atl/codesnippet/cpp/catlarray-class_11.cpp)]  
  
##  <a name="setat"></a>CAtlArray::SetAt  
 Bir öğenin değeri dizi nesnesinin ayarlamak için bu yöntemi çağırın.  
  
```
void SetAt(size_t iElement, INARGTYPE element);
```  
  
### <a name="parameters"></a>Parametreler  
 `iElement`  
 Ayarlanacak dizi öğesine işaret eden dizini.  
  
 `element`  
 Belirtilen öğe yeni değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata ayıklama derlemelerinde bir ATLASSERT gerçekleştirilecektir `iElement` dizideki öğelerin sayısını aşıyor. Perakende derlemelerde geçersiz bir parametre öngörülemeyen sonuçlara neden olabilir.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlArray::GetAt](#getat).  
  
##  <a name="setcount"></a>CAtlArray::SetCount  
 Dizi nesnesi boyutunu ayarlamak için bu yöntemi çağırın.  
  
```
bool SetCount(size_t nNewSize, int nGrowBy = - 1);
```  
  
### <a name="parameters"></a>Parametreler  
 `nNewSize`  
 Dizi gerekli boyutu.  
  
 `nGrowBy`  
 Belirlemek için kullanılan bir değeri arabellek yapmak için ne kadar büyük. -1 değeri, dahili olarak hesaplanan bir değerin kullanılabilmesi için neden olur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizi Aksi halde başarıyla yeniden boyutlandırılan, false ise, true döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Dizi artırılabilir veya boyutu azaltılabilir. Artan fazladan boş öğeleri dizi olarak eklenir. Azaltılabilir, en büyük dizinler öğeleriyle silinecek ve bellek serbest.  
  
 Kullanmadan önce dizinin boyutunu ayarlamak için bu yöntemi kullanın. Varsa `SetCount` kullanılmaz, öğeleri ekleme işlemini — ve sonraki bellek ayırma gerçekleştirilen — performansı düşürebilir ve parçalara bellek.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlArray::GetData](#getdata).  
  
##  <a name="setatgrow"></a>CAtlArray::SetAtGrow  
 Bir dizi gerekli olarak genişletme dizi nesnesi, bir öğenin değerini ayarlamak için bu yöntemi çağırın.  
  
```
void SetAtGrow(size_t iElement, INARGTYPE element);
```  
  
### <a name="parameters"></a>Parametreler  
 `iElement`  
 Ayarlanacak dizi öğesine işaret eden dizini.  
  
 `element`  
 Belirtilen öğe yeni değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Dizine göre işaret öğenin değerini değiştirir. Varsa `iElement` geçerli boyuttan büyük dizi dizi otomatik olarak yapılan bir çağrı kullanılarak artırılır [CAtlArray::SetCount](#setcount). Hata ayıklama derlemelerinde bir ATLASSERT gerçekleştirilecektir `CAtlArray` nesnesi geçerli değil. Perakende derlemelerde geçersiz parametreler öngörülemeyen sonuçlara neden olabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#12](../../atl/codesnippet/cpp/catlarray-class_12.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MMXSwarm örnek](../../visual-cpp-samples.md)   
 [DynamicConsumer örnek](../../visual-cpp-samples.md)   
 [Oluşturma](../../visual-cpp-samples.md)   
 [Kayan örnek](../../visual-cpp-samples.md)   
 [CArray sınıfı](../../mfc/reference/carray-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
