---
title: CArray sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CArray
- AFXTEMPL/CArray
- AFXTEMPL/CArray::CArray
- AFXTEMPL/CArray::Add
- AFXTEMPL/CArray::Append
- AFXTEMPL/CArray::Copy
- AFXTEMPL/CArray::ElementAt
- AFXTEMPL/CArray::FreeExtra
- AFXTEMPL/CArray::GetAt
- AFXTEMPL/CArray::GetCount
- AFXTEMPL/CArray::GetData
- AFXTEMPL/CArray::GetSize
- AFXTEMPL/CArray::GetUpperBound
- AFXTEMPL/CArray::InsertAt
- AFXTEMPL/CArray::IsEmpty
- AFXTEMPL/CArray::RemoveAll
- AFXTEMPL/CArray::RemoveAt
- AFXTEMPL/CArray::SetAt
- AFXTEMPL/CArray::SetAtGrow
- AFXTEMPL/CArray::SetSize
dev_langs:
- CPP
helpviewer_keywords:
- CArray [MFC], CArray
- CArray [MFC], Add
- CArray [MFC], Append
- CArray [MFC], Copy
- CArray [MFC], ElementAt
- CArray [MFC], FreeExtra
- CArray [MFC], GetAt
- CArray [MFC], GetCount
- CArray [MFC], GetData
- CArray [MFC], GetSize
- CArray [MFC], GetUpperBound
- CArray [MFC], InsertAt
- CArray [MFC], IsEmpty
- CArray [MFC], RemoveAll
- CArray [MFC], RemoveAt
- CArray [MFC], SetAt
- CArray [MFC], SetAtGrow
- CArray [MFC], SetSize
ms.assetid: fead8b00-4cfd-4625-ad0e-251df62ba92f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 53089439c3857dd947a263a80f3330aad3f03f7b
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37339444"
---
# <a name="carray-class"></a>CArray sınıfı
C dizilerine olan ancak dinamik olarak azaltmak ve gerektikçe büyütün dizilerini destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class TYPE, class ARG_TYPE = const TYPE&>  
class CArray : public CObject  
```  
  
#### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Şablon parametresi dizide depolanan nesnelerin türünü belirtir. *TÜR* tarafından döndürülen bir parametredir `CArray`.  
  
 *ARG* *_* *TÜRÜ*  
 Şablon parametresi dizisinde depolanan nesnelere erişmek için kullanılan bağımsız değişken türü belirtir. Genellikle bir başvuru *türü*. *ARG_TYPE* geçirilen bir parametre `CArray`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CArray::CArray](#carray)|Boş bir dizi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CArray::Add](#add)|Dizinin sonuna bir öğe ekler; dizi gerekirse büyür.|  
|[CArray::Append](#append)|Diziyi başka diziye ekler; Gerekirse, dizi büyüyor|  
|[CArray::Copy](#copy)|Diziyi başka diziye kopyalar; dizi gerekirse büyür.|  
|[CArray::ElementAt](#elementat)|Dizi içinde öğe işaretçisi için geçici bir başvuru döndürür.|  
|[CArray::FreeExtra](#freeextra)|Geçerli üst sınır yukarıdaki tüm kullanılmayan belleği serbest bırakır.|  
|[CArray::GetAt](#getat)|Belirtilen dizindeki değeri döndürür.|  
|[CArray::GetCount](#getcount)|Bu dizinin içinde öğe sayısını alır.|  
|[CArray::GetData](#getdata)|Dizide öğelere erişim sağlar. NULL olabilir.|  
|[CArray::GetSize](#getsize)|Bu dizinin içinde öğe sayısını alır.|  
|[CArray::GetUpperBound](#getupperbound)|En büyük geçerli dizinini döndürür.|  
|[CArray::InsertAt](#insertat)|Belirtilen dizindeki öğenin (veya başka bir dizideki tüm öğeler) ekler.|  
|[CArray::IsEmpty](#isempty)|Dizi boş olup olmadığını belirler.|  
|[CArray::RemoveAll](#removeall)|Bu dizisinden tüm öğeleri kaldırır.|  
|[CArray::RemoveAt](#removeat)|Belirli bir dizindeki öğeyi kaldırır.|  
|[CArray::SetAt](#setat)|Belirtilen dizin için değeri ayarlar; dizi büyümesine izin verilmiyor.|  
|[CArray::SetAtGrow](#setatgrow)|Belirtilen dizin için değeri ayarlar; dizi gerekirse büyür.|  
|[CArray::SetSize](#setsize)|Bu dizinin içinde yer alması için öğe sayısını ayarlar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[işleci&#91;&#93;](#operator_at)|Belirtilen dizindeki öğeyi alır veya ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Dizi dizinleri her zaman 0 konumunda başlar. Üst sınır düzeltin veya bağlı geçerli geçmiş öğeler eklediğinizde, genişletmek bir dizi etkinleştirmek karar verebilirsiniz. Bazı öğeler null olsa bile, bellek için üst sınır, bitişik ayrılır.  
  
> [!NOTE]
>  Yeniden boyutlandırma çoğu yöntemleri bir `CArray` nesne veya ona öğelerini kullanma ekleme [memcpy_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md) öğeleri taşımak için. Bunun nedeni bir sorun, `memcpy_s` çağrılacak oluşturucunun gerektiren herhangi bir nesne ile uyumlu değil. Varsa öğeleri `CArray` ile uyumlu `memcpy_s`, yeni bir oluşturmalısınız `CArray` uygun boyutta. Ardından kullanmalısınız [CArray::Copy](#copy) ve [CArray::SetAt](#setat) bu yöntemleri yerine bir atama işleci kullandığından, yeni bir dizi doldurmak için `memcpy_s`.  
  
 Bir C dizi için erişim zamanı olduğu gibi bir `CArray` dizinlenmiş öğeye sabittir ve dizi boyutu bağımsızdır.  
  
> [!TIP]
>  Bir dizi kullanmadan önce kullanmayı [SetSize](#setsize) boyutuna kurmak ve kendisi için bellek ayrılamadı. Kullanmıyorsanız, `SetSize`, diziniz için öğeleri ekleme, oluyor, sık sık yeniden ve kopyalanır. Sık sık yeniden ayırma ve kopyalama verimsiz ve bellek parçası.  
  
 Bir dizideki tek tek öğelerin dökümü gerekiyorsa derinliğini ayarlamalısınız [CDumpContext](../../mfc/reference/cdumpcontext-class.md) 1 veya daha büyük bir nesne.  
  
 Bu sınıf, genel yardımcı işlevleri çağrının belirli üye işlevleri, çoğu kullanım için özelleştirilmelidir `CArray` sınıfı. Konusuna [koleksiyon sınıfı Yardımcıları](../../mfc/reference/collection-class-helpers.md) MFC makroları ve genel öğeleri bölümünde.  
  
 Array sınıfı türetme gibi liste türetme ' dir.  
  
 Nasıl kullanılacağı hakkında daha fazla bilgi için `CArray`, makaleye göz atın [koleksiyonları](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CArray`  
  
## <a name="requirements"></a>Gereksinimler  
 `Header:` afxtempl.h  
  
##  <a name="add"></a>  CArray::Add  
 1 ile dizi büyüyen bir dizinin sonuna yeni bir öğe ekler.  
  
```  
INT_PTR Add(ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parametreler  
 *ARG_TYPE*  
 Şablon parametresi bu dizideki öğelerin başvuran bir bağımsız değişken türünü belirleme.  
  
 *newElement*  
 Bu diziye eklenecek öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eklenen öğenin dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa [SetSize](#setsize) ile kullanılan bir `nGrowBy` değeri 1 ve ardından ek bellek büyük ayrılan. Bununla birlikte, üst sınırı yalnızca 1 artar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#22](../../mfc/codesnippet/cpp/carray-class_1.cpp)]  
  
##  <a name="append"></a>  CArray::Append  
 Bir dizinin içeriğini başka bir sonuna eklemek için bu üye işlevini çağırın.  
  
```  
INT_PTR Append(const CArray& src);
```  
  
### <a name="parameters"></a>Parametreler  
 *src*  
 Kaynak bir diziye eklenecek öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eklenen ilk öğenin dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Diziler, aynı türde olmalıdır.  
  
 Gerekirse, `Append` diziye eklenen öğeleri uyum sağlamak için ek bellek ayırabilirsiniz.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#23](../../mfc/codesnippet/cpp/carray-class_2.cpp)]  
  
##  <a name="carray"></a>  CArray::CArray  
 Boş bir dizi oluşturur.  
  
```  
CArray();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Diziye bir öğe aynı anda büyür.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#24](../../mfc/codesnippet/cpp/carray-class_3.cpp)]  
  
##  <a name="copy"></a>  CArray::Copy  
 Bu üye işlevi, bir dizinin öğeleri diğerine kopyalamak için kullanın.  
  
```  
void Copy(const CArray& src);
```  
  
### <a name="parameters"></a>Parametreler  
 *src*  
 Bir diziye kopyalanacak öğe kaynağı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir dizinin öğeleri başka bir dizinin öğeleri ile üzerine yazmak için bu üye işlevini çağırın.  
  
 `Copy` belleği boşaltmak değil; Ancak, gerekirse `Copy` diziye kopyalanan öğelerin uyum sağlamak için ek bellek ayırabilirsiniz.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#25](../../mfc/codesnippet/cpp/carray-class_4.cpp)]  
  
##  <a name="elementat"></a>  CArray::ElementAt  
 Dizi içinde belirtilen öğeye geçici bir başvuru döndürür.  
  
```  
TYPE& ElementAt(INT_PTR nIndex);  
const TYPE& ElementAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Büyük veya 0'a eşit bir tamsayı dizini ve tarafından döndürülen değer küçüktür veya eşittir [GetUpperBound](#getupperbound).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir dizi öğesine bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Diziler için sol taraftaki atama işleci uygulamak için kullanılır.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [GetSize](#getsize).  
  
##  <a name="freeextra"></a>  CArray::FreeExtra  
 Dizi büyütmüş sırada ayrılmış ek bellek kazandırır.  
  
```  
void FreeExtra();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev boyutu veya dizi üst sınırı üzerinde etkisi yoktur.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [GetData](#getdata).  
  
##  <a name="getat"></a>  CArray::GetAt  
 Dizi belirtilen dizindeki öğeyi döndürür.  
  
```  
TYPE& GetAt(INT_PTR nIndex);  
const TYPE& GetAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Şablon parametresi dizi öğelerinin türünü belirterek.  
  
 *nIndex*  
 Büyük veya 0'a eşit bir tamsayı dizini ve tarafından döndürülen değer küçüktür veya eşittir [GetUpperBound](#getupperbound).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şu anda bu dizinde dizi öğesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Negatif bir değer veya bir değer döndürdüğü değerden geçirme `GetUpperBound` başarısız bir onaylama işlemi neden olur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#26](../../mfc/codesnippet/cpp/carray-class_5.cpp)]  
  
##  <a name="getcount"></a>  CArray::GetCount  
 Dizi öğelerinin sayısını döndürür.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizideki öğelerin sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Dizideki öğelerin sayısını almak için bu yöntemi çağırın. Dizinler sıfır tabanlı olduğundan, boyutu en büyük dizinden daha büyük olan 1 ' dir. Bu yöntemin çağrılması aynı sonucu üretir [CArray::GetSize](#getsize) yöntemi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#27](../../mfc/codesnippet/cpp/carray-class_6.cpp)]  
  
##  <a name="getdata"></a>  CArray::GetData  
 Bu üye işlevi bir dizideki öğelerin doğrudan erişim elde etmek için kullanın.  
  
```  
const TYPE* GetData() const; 
TYPE* GetData();
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Şablon parametresi dizi öğelerinin türünü belirterek.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir dizi öğesinin işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Hiçbir öğe varsa `GetData` bir null değer döndürür.  
  
 Bir dizinin öğeleri doğrudan erişim daha hızlı çalışmanıza yardımcı olabilir, ancak çağırırken dikkatli `GetData`; doğrudan yaptığınız herhangi bir hata, dizinin öğeleri etkiler.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#28](../../mfc/codesnippet/cpp/carray-class_7.cpp)]  
  
##  <a name="getsize"></a>  CArray::GetSize  
 Dizinin boyutunu döndürür.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dizinler sıfır tabanlı olduğundan, boyutu en büyük dizinden daha büyük olan 1 ' dir. Bu yöntemin çağrılması aynı sonucu üretir [CArray::GetCount](#getcount) yöntemi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#29](../../mfc/codesnippet/cpp/carray-class_8.cpp)]  
  
##  <a name="getupperbound"></a>  CArray::GetUpperBound  
 Bu dizinin geçerli üst sınırını döndürür.  
  
```  
INT_PTR GetUpperBound() const;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dizi dizinleri sıfır tabanlı olduğundan, bu işlev, 1 değerini döndürür. kısa `GetSize`.  
  
 Koşul `GetUpperBound( )` = -1, dizi hiç öğe içerdiğini gösterir.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CArray::GetAt](#getat).  
  
##  <a name="insertat"></a>  CArray::InsertAt  
 Ürününün ilk sürümünü `InsertAt` belirli bir dizinden bir dizideki bir öğe (veya birden çok kopyasını bir öğe) ekler.  
  
```  
void InsertAt(
    INT_PTR nIndex,
    ARG_TYPE newElement,  
    INT_PTR nCount = 1);
 
void InsertAt(
    INT_PTR nStartIndex,  
    CArray* pNewArray);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Tarafından döndürülen değeri,'den büyük bir tamsayı dizini `GetUpperBound`.  
  
 *ARG_TYPE*  
 Şablon parametresi bu dizideki öğelerin türünü belirtme.  
  
 *newElement*  
 Bu dizinin içinde yer öğesi.  
  
 *nCount*  
 Bu öğe olmalıdır sayısı (varsayılan 1) eklenir.  
  
 *nStartIndex*  
 Tarafından döndürülen değeri,'den büyük bir tamsayı dizini [GetUpperBound](#getupperbound).  
  
 *pNewArray*  
 Bu diziye eklenecek öğeleri içeren başka bir dizi.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlem sırasında yukarı kaydırır (dizin artırılarak) ve bu dizin mevcut öğe üzerindeki tüm öğeleri yukarı kaydırır.  
  
 Dosyanın ikinci sürümü tüm öğeleri bir diğerinden ekler `CArray` başlayarak koleksiyon *nStartIndex* konumu.  
  
 `SetAt` İşlevi, buna karşılık, bir belirtilen dizi öğesi değiştirir ve tüm öğeleri kaydırmak değil.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#30](../../mfc/codesnippet/cpp/carray-class_9.cpp)]  
  
##  <a name="isempty"></a>  CArray::IsEmpty  
 Dizi boş olup olmadığını belirler.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizi hiçbir öğe içeren olursa sıfır dışı; Aksi durumda 0.  
  
##  <a name="operator_at"></a>  CArray::operator \[\]  
 Bu alt simge işleçlerini için kullanışlı bir alternatif olan [SetAt](#setat) ve [GetAt](#getat) işlevleri.  
  
```  
TYPE& operator[](int_ptr nindex);  
const TYPE& operator[](int_ptr nindex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Şablon parametresi bu dizideki öğelerin türünü belirtme.  
  
 *nIndex*  
 Erişilecek öğenin dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk işleç değil diziler için çağrılır **const**, sağ (r) veya Atama ifadesinin solunda (lvalue) üzerinde kullanılabilir. İkinci adında için **const** diziler, yalnızca sağ tarafta kullanılır.  
  
 Kitaplığı hata ayıklama sürümünü (veya sol veya sağ tarafında bir atama ifadesi) alt simge sınırların dışında olup olmadığını onaylar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#34](../../mfc/codesnippet/cpp/carray-class_10.cpp)]  
  
##  <a name="relocateelements"></a>  CArray::RelocateElements  
 Dizi büyüyebilen veya küçülebilen, veri için yeni bir arabellek yeniden yerleştirir.  
  
```  
template<class TYPE, class ARG_TYPE>  
AFX_INLINE void CArray<TYPE, ARG_TYPE>::RelocateElements(
    TYPE* pNewData,  
    const TYPE* pData,  
    INT_PTR nCount);
```  
  
### <a name="parameters"></a>Parametreler  
 *pNewData*  
 Yeni bir arabellek için öğeleri dizisi.  
  
 *pData*  
 Eski öğeleri dizisi.  
  
 *nCount*  
 Eski dizideki öğelerin sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 *pNewData* her zaman tüm tutabilecek kadar büyük olduğundan *pData* öğeleri.  
  
 [CArray](../../mfc/reference/carray-class.md) uygulaması, dizi büyüyebilen veya küçülebilen, eski verileri için yeni bir arabellek kopyalamak için bu yöntemi kullanır (zaman [SetSize](#setsize) veya [FreeExtra](#freeextra) olarak adlandırılır). Varsayılan uygulama, yalnızca veri kopyalar.  
  
 Kendi üyelerinden biri için bir işaretçi bir öğe içeriyorsa veya başka bir yapı bir dizi öğeleri için bir işaretçi içeren diziler için işaretçiler düz kopya güncelleştirilir. Bu durumda, bir alt uzmanlaşması uygulayarak işaretçileri düzeltebilirsiniz `RelocateElements` ilgili türleri ile. Ayrıca veri kopyalamak için sizin sorumluluğunuzdadır.  
  
##  <a name="removeall"></a>  CArray::RemoveAll  
 Bu dizisinden tüm öğeleri kaldırır.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dizi zaten boşsa, işlev hala çalışır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#31](../../mfc/codesnippet/cpp/carray-class_11.cpp)]  
  
##  <a name="removeat"></a>  CArray::RemoveAt  
 Bir dizideki belirli bir dizinden başlayarak bir veya daha fazla öğeleri kaldırır.  
  
```  
void RemoveAt(
    INT_PTR nIndex,  
    INT_PTR nCount = 1);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Büyük veya 0'a eşit bir tamsayı dizini ve tarafından döndürülen değer küçüktür veya eşittir [GetUpperBound](#getupperbound).  
  
 *nCount*  
 Kaldırılacak öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlem sırasında kaldırılan öğeyi/öğeleri yukarıdaki tüm öğeleri aşağı kaydırır. Bu üst dizisi bağlı, ancak bellek serbest değil azaltır.  
  
 Dizideki kaldırma noktası yukarıda yer alan çok daha fazla öğe ekleyip denerseniz, ardından kitaplığı hata ayıklama sürümünü onaylar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#32](../../mfc/codesnippet/cpp/carray-class_12.cpp)]  
  
##  <a name="setat"></a>  CArray::SetAt  
 Belirtilen dizindeki dizi öğesini ayarlar.  
  
```  
void SetAt(INT_PTR nIndex, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Büyük veya 0'a eşit bir tamsayı dizini ve tarafından döndürülen değer küçüktür veya eşittir [GetUpperBound](#getupperbound).  
  
 *ARG_TYPE*  
 Dizi öğelerine başvurmak için kullanılan bağımsız değişkenleri türünü belirten bir şablon parametre.  
  
 *newElement*  
 Belirtilen konumda depolanan yeni öğe değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 `SetAt` dizi büyümesine neden. Kullanım [SetAtGrow](#setatgrow) otomatik olarak büyütmeyi dizi istiyorsanız.  
  
 Dizin değerinizi dizisindeki geçerli bir konum temsil eder emin olmanız gerekir. Sınırların dışında ise, ardından kitaplığı hata ayıklama sürümünü onaylar.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [GetAt](#getat).  
  
##  <a name="setatgrow"></a>  CArray::SetAtGrow  
 Belirtilen dizindeki dizi öğesini ayarlar.  
  
```  
void SetAtGrow(INT_PTR nIndex, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Büyük veya 0'a eşit bir tamsayı dizini.  
  
 *ARG_TYPE*  
 Şablon parametresi dizideki öğelerin türünü belirtme.  
  
 *newElement*  
 Bu diziye eklenecek öğe. NULL değerine izin verilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Gerekirse, dizi otomatik olarak artar (diğer bir deyişle, üst sınırı yeni öğeye uyum sağlamak için ayarlanır).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#33](../../mfc/codesnippet/cpp/carray-class_13.cpp)]  
  
##  <a name="setsize"></a>  CArray::SetSize  
 Boş veya varolan bir dizinin boyutunu belirler; Gerekirse, bellek ayırır.  
  
```  
void SetSize(
    INT_PTR nNewSize,  
    INT_PTR nGrowBy = -1);
```  
  
### <a name="parameters"></a>Parametreler  
 *nNewSize*  
 Yeni dizi boyutu (öğe sayısı). Büyük veya 0'a eşit olmalıdır.  
  
 *nGrowBy*  
 Öğe yuvaları boyutu artışı gerekliyse ayrılacak en küçük sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni boyut eski boyuttan daha küçükse, dizi kesilmiş ve tüm kullanılmayan belleği serbest kalır.  
  
 Dizi kullanmaya başlamadan önce dizinin boyutunu ayarlamak için bu işlevi kullanın. Kullanmıyorsanız, `SetSize`, diziniz için öğeleri ekleme, oluyor, sık sık yeniden ve kopyalanır. Sık sık yeniden ayırma ve kopyalama verimsiz ve bellek parçası.  
  
 *NGrowBy* parametre dizi artan sırada iç bellek ayırma etkiler. Kullanımı hiçbir zaman tarafından raporlandığı şekilde dizi boyutu etkiler [GetSize](#getsize) ve [GetUpperBound](#getupperbound). Varsayılan değer kullandıysanız, MFC Bellek parçalanması önlemek ve verimliliği çoğu durum için en iyi duruma getirmek için hesaplanan bir şekilde bellek ayırır.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [GetData](#getdata).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek Topla](../../visual-cpp-samples.md)   
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CObArray sınıfı](../../mfc/reference/cobarray-class.md)   
 [Koleksiyon Sınıfı Yardımcıları](../../mfc/reference/collection-class-helpers.md)
