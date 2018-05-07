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
ms.openlocfilehash: 4e4e4fd0106687927706b0ba303035258de7e651
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="carray-class"></a>CArray sınıfı
C dizi gibi olan, ancak dinamik olarak azaltmak ve gerektikçe büyütün diziler destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class TYPE, class ARG_TYPE = const TYPE&>  
class CArray : public CObject  
```  
  
#### <a name="parameters"></a>Parametreler  
 `TYPE`  
 Şablon parametresi dizisinde depolanan nesneler türünü belirtir. `TYPE` tarafından döndürülen bir parametre olan `CArray`.  
  
 `ARG` *_* `TYPE`  
 Şablon parametresi dizisinde depolanan nesnelere erişmek için kullanılan bağımsız değişken türü belirtir. Genellikle başvuru `TYPE`. `ARG_TYPE` Geçirilen parametre `CArray`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CArray::CArray](#carray)|Boş bir dizi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CArray::Add](#add)|Bir öğeyi dizinin sonuna ekler; dizi gerekirse artar.|  
|[CArray::Append](#append)|Başka bir dizi diziye ekler; Gerekirse, dizi büyümesi|  
|[CArray::Copy](#copy)|Başka bir dizi diziye kopyalar; dizi gerekirse artar.|  
|[CArray::ElementAt](#elementat)|Dizi öğesi işaretçinin geçici bir başvuru döndürür.|  
|[CArray::FreeExtra](#freeextra)|Geçerli bir üst sınır yukarıdaki tüm kullanılmayan belleği serbest bırakır.|  
|[CArray::GetAt](#getat)|Belirtilen dizindeki değeri döndürür.|  
|[CArray::GetCount](#getcount)|Bu dizide öğe sayısını alır.|  
|[CArray::GetData](#getdata)|Dizideki öğelere erişim sağlar. Olabilir **NULL**.|  
|[CArray::GetSize](#getsize)|Bu dizide öğe sayısını alır.|  
|[CArray::GetUpperBound](#getupperbound)|En büyük geçerli dizinini döndürür.|  
|[CArray::InsertAt](#insertat)|Bir öğenin (veya başka bir dizinin tüm öğeleri) belirtilen bir dizinde ekler.|  
|[CArray::IsEmpty](#isempty)|Dizi boş olup olmadığını belirler.|  
|[CArray::RemoveAll](#removeall)|Bu dizisinden tüm öğeleri kaldırır.|  
|[CArray::RemoveAt](#removeat)|Belirli bir dizinindeki bir öğeyi kaldırır.|  
|[CArray::SetAt](#setat)|Belirli bir dizine için değeri ayarlar; dizi büyümeye izin verilmiyor.|  
|[CArray::SetAtGrow](#setatgrow)|Belirli bir dizine için değeri ayarlar; dizi gerekirse artar.|  
|[CArray::SetSize](#setsize)|Bu dizide dahil edilmek üzere öğe sayısını ayarlar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[işleci&#91;&#93;](#operator_at)|Belirtilen dizindeki öğeyi alır veya ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Dizi dizinleri her zaman 0 konumunda başlatın. Üst sınır düzeltin veya bağlı geçerli geçmiş öğeleri eklediğinizde genişletmek dizi etkinleştirmek karar verebilirsiniz. Bazı öğeler null olsa bile bellek üst sınırı için bitişik ayrılır.  
  
> [!NOTE]
>  Yeniden boyutlandırma çoğu yöntemleri bir `CArray` nesne veya ona öğelerini kullanan eklemek [memcpy_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md) öğeleri taşımak için. Bu bir sorun olduğundan `memcpy_s` çağrılacak Oluşturucusu gerektiren tüm nesneler ile uyumlu değil. Öğeler `CArray` ile uyumlu değil `memcpy_s`, yeni bir oluşturmalısınız `CArray` uygun boyutta. Ardından kullanmalısınız [CArray::Copy](#copy) ve [CArray::SetAt](#setat) atama işleci yerine bu yöntemi kullanmak için yeni bir dizi doldurmak için `memcpy_s`.  
  
 Bir C dizi için erişim süresi ile bir `CArray` dizinli öğe sabit öğesidir ve dizi boyutundan bağımsızdır.  
  
> [!TIP]
>  Bir dizi kullanmadan önce kullanın [SetSize](#setsize) boyutuna kurmak ve bunun için bellek ayrılamadı. Kullanmıyorsanız, `SetSize`, dizinizi için öğe eklemek görüntülenmesine neden olur sık bırakılan ve kopyalanır. Sık sık yeniden ayırma ve kopyalama verimsiz ve bellek parçalara.  
  
 Bir dizi ayrı ayrı öğeler dökümü gerekiyorsa, derinliğini ayarlamalısınız [CDumpContext](../../mfc/reference/cdumpcontext-class.md) nesneyi 1 veya daha büyük.  
  
 Genel yardımcı işlevleri sınıfı çağrısı belirli üye işlevleri için çoğu kullanımlarını özelleştirilmelidir `CArray` sınıfı. Konusuna [koleksiyon sınıfı Yardımcıları](../../mfc/reference/collection-class-helpers.md) MFC makroları ve genel öğeleri bölümünde.  
  
 Array sınıfı türetme listesi türetme gibi ' dir.  
  
 Nasıl kullanılacağı hakkında daha fazla bilgi için `CArray`, makaleye bakın [koleksiyonları](../../mfc/collections.md).  
  
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
 `ARG_TYPE`  
 Bu dizideki öğeler başvuran bağımsız değişken türünü belirten bir şablon parametre.  
  
 `newElement`  
 Bu diziye eklenecek öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eklenen öğenin dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa [SetSize](#setsize) ile kullanılan bir `nGrowBy` 1 sonra ek bellek büyük bir değer ayrılamadı. Ancak, üst sınır tarafından yalnızca 1 artacaktır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#22](../../mfc/codesnippet/cpp/carray-class_1.cpp)]  
  
##  <a name="append"></a>  CArray::Append  
 Bir dizinin içeriğini başka sonuna eklemek için bu üye işlevini çağırın.  
  
```  
INT_PTR Append(const CArray& src);
```  
  
### <a name="parameters"></a>Parametreler  
 *src*  
 Kaynağı için bir dizi eklenecek öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk eklenmiş öğenin dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Diziler, aynı türde olmalıdır.  
  
 Gerekirse, **Append** diziye eklenen öğeleri yerleştirmek için ek bellek ayırabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#23](../../mfc/codesnippet/cpp/carray-class_2.cpp)]  
  
##  <a name="carray"></a>  CArray::CArray  
 Boş bir dizi oluşturur.  
  
```  
CArray();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dizi bir öğe aynı anda artar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#24](../../mfc/codesnippet/cpp/carray-class_3.cpp)]  
  
##  <a name="copy"></a>  CArray::Copy  
 Bir dizinin öğeleri diğerine kopyalamak için bu üye işlevini kullanın.  
  
```  
void Copy(const CArray& src);
```  
  
### <a name="parameters"></a>Parametreler  
 *src*  
 Kaynak öğelerin bir diziye kopyalar.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir dizinin öğeleri başka bir dizi öğelerle üzerine yazmak için bu üye işlevini çağırın.  
  
 **Kopya** belleği serbest değil; ancak, gerekirse, **kopyalama** diziye kopyalanan öğelerin uyum sağlamak için ek bellek ayırabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#25](../../mfc/codesnippet/cpp/carray-class_4.cpp)]  
  
##  <a name="elementat"></a>  CArray::ElementAt  
 Dizi içinde belirtilen öğeye geçici bir başvuru döndürür.  
  
```  
TYPE& ElementAt(INT_PTR nIndex);  
const TYPE& ElementAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Büyük veya 0 değerine eşit bir tamsayı dizini ve tarafından döndürülen değer eşit veya daha az [GetUpperBound](#getupperbound).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir dizi öğesine başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Diziler için sol taraftaki atama işleci uygulamak için kullanılır.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [GetSize](#getsize).  
  
##  <a name="freeextra"></a>  CArray::FreeExtra  
 Dizi büyütülen sırada ayrılmış ek bellek boşaltır.  
  
```  
void FreeExtra();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev boyutunu veya dizi üst sınırının üzerinde etkisi yoktur.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [GetData](#getdata).  
  
##  <a name="getat"></a>  CArray::GetAt  
 Belirtilen dizindeki dizi öğesi döndürür.  
  
```  
TYPE& GetAt(INT_PTR nIndex);  
const TYPE& GetAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Dizi öğeleri türünü belirten bir şablon parametre.  
  
 `nIndex`  
 Büyük veya 0 değerine eşit bir tamsayı dizini ve tarafından döndürülen değer eşit veya daha az [GetUpperBound](#getupperbound).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şu anda bu dizinindeki dizi öğe.  
  
### <a name="remarks"></a>Açıklamalar  
 Negatif bir değer veya bir değer tarafından döndürülen değeri büyük geçirme `GetUpperBound` içinde başarısız onaylama neden olur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#26](../../mfc/codesnippet/cpp/carray-class_5.cpp)]  
  
##  <a name="getcount"></a>  CArray::GetCount  
 Dizi öğe sayısını döndürür.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizideki öğelerin sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Dizideki öğelerin sayısını almak için bu yöntemi çağırın. Dizinleri sıfır tabanlı olduğundan, 1'den büyük dizin büyük boyutudur. Bu yöntemin çağrılması aynı sonucu oluşturacağını [CArray::GetSize](#getsize) yöntemi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#27](../../mfc/codesnippet/cpp/carray-class_6.cpp)]  
  
##  <a name="getdata"></a>  CArray::GetData  
 Bir dizideki öğeler doğrudan erişmek için bu üye işlevini kullanın.  
  
```  
const TYPE* GetData() const; 
TYPE* GetData();
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Dizi öğeleri türünü belirten bir şablon parametre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizi öğesi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Öğe varsa, `GetData` null değeri döndürür.  
  
 Dizi öğelerini doğrudan erişim daha hızlı çalışmanıza yardımcı olabilir, ancak çağrılırken dikkatli `GetData`; doğrudan yaptığınız herhangi bir hata dizinizi öğelerini etkiler.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#28](../../mfc/codesnippet/cpp/carray-class_7.cpp)]  
  
##  <a name="getsize"></a>  CArray::GetSize  
 Dizinin boyutu döndürür.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dizinleri sıfır tabanlı olduğundan, 1'den büyük dizin büyük boyutudur. Bu yöntemin çağrılması aynı sonucu oluşturacağını [CArray::GetCount](#getcount) yöntemi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#29](../../mfc/codesnippet/cpp/carray-class_8.cpp)]  
  
##  <a name="getupperbound"></a>  CArray::GetUpperBound  
 Bu dizinin geçerli üst sınırının döndürür.  
  
```  
INT_PTR GetUpperBound() const;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dizi dizinleri sıfır tabanlı olduğundan, bu işlev, 1 değerini döndürür. değerinden `GetSize`.  
  
 Koşul **GetUpperBound ()** = -1 gösterir dizi öğe içeriyor.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CArray::GetAt](#getat).  
  
##  <a name="insertat"></a>  CArray::InsertAt  
 İlk sürümü `InsertAt` bir öğenin (veya birden çok kopya, bir öğenin) bir dizi belirtilen dizinde ekler.  
  
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
 `nIndex`  
 Tarafından döndürülen değeri,'den büyük bir tamsayı dizini `GetUpperBound`.  
  
 `ARG_TYPE`  
 Bu dizide öğelerin türünü belirten bir şablon parametre.  
  
 `newElement`  
 Bu dizide yerleştirilecek öğesi.  
  
 `nCount`  
 Bu öğe olmalıdır sayısı (varsayılan 1) ekledi.  
  
 `nStartIndex`  
 Tarafından döndürülen değeri,'den büyük bir tamsayı dizini [GetUpperBound](#getupperbound).  
  
 `pNewArray`  
 Bu diziye eklenecek öğeleri içeren başka bir dizi.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlem sırasında yapılandırmasına kayar (dizini artırılarak) ve bu dizin mevcut öğede üzerindeki tüm öğeleri yukarı kaydırır.  
  
 İkinci Sürüm tüm öğeleri diğerinden ekler `CArray` başlayarak koleksiyon `nStartIndex` konumu.  
  
 `SetAt` İşlevi, buna karşılık, bir belirtilen dizi öğesi değiştirir ve herhangi bir öğe shift değil.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#30](../../mfc/codesnippet/cpp/carray-class_9.cpp)]  
  
##  <a name="isempty"></a>  CArray::IsEmpty  
 Dizi boş olup olmadığını belirler.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizi öğe içeriyorsa sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="operator_at"></a>  CArray::operator \[\]  
 Bu alt simge işleçlerini için uygun bir alternatif olan [SetAt](#setat) ve [GetAt](#getat) işlevleri.  
  
```  
TYPE& operator[](int_ptr nindex);  
const TYPE& operator[](int_ptr nindex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Bu dizide öğelerin türünü belirten bir şablon parametre.  
  
 `nIndex`  
 Erişilecek öğenin dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk işleci adlı olmayan diziler için **const**, sağ (r) veya Atama ifadesinin sol (l-değeri) üzerinde kullanılabilir. İkinci olarak adlandırılan için **const** dizileri, yalnızca sağ tarafta kullanılır.  
  
 Alt simge (ya da sol veya sağ tarafında Atama ifadesinin) sınırların dışında olup olmadığını kitaplığının hata ayıklama sürümü onaylar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#34](../../mfc/codesnippet/cpp/carray-class_10.cpp)]  
  
##  <a name="relocateelements"></a>  CArray::RelocateElements  
 Dizi büyümesine ya da küçültmek verileri için yeni bir arabellek yeniden yerleştirir.  
  
```  
template<class TYPE, class ARG_TYPE>  
AFX_INLINE void CArray<TYPE, ARG_TYPE>::RelocateElements(
    TYPE* pNewData,  
    const TYPE* pData,  
    INT_PTR nCount);
```  
  
### <a name="parameters"></a>Parametreler  
 `pNewData`  
 Öğeleri dizisi için yeni bir arabellek.  
  
 `pData`  
 Eski öğeleri dizisi.  
  
 `nCount`  
 Eski dizideki öğelerin sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 `pNewData` her zaman tüm tutmak için yeterince büyük olduğundan `pData` öğeleri.  
  
 [CArray](../../mfc/reference/carray-class.md) uygulama dizi büyütür veya küçültmek zaman yeni bir arabellek eski verileri kopyalamak için bu yöntemi kullanır (zaman [SetSize](#setsize) veya [FreeExtra](#freeextra) denir). Varsayılan uygulama, yalnızca verileri kopyalar.  
  
 Kendi üyelerinden biri için bir işaretçi bir öğe içeriyor veya başka bir yapı bir dizi öğelerinin bir işaretçi içeriyor diziler için işaretçileri düz kopyasında güncelleştirilmez. Bu durumda, bir alt uzmanlaşması uygulayarak işaretçileri düzeltebilirsiniz `RelocateElements` ilgili türleri ile. Ayrıca veri kopyalamak için sorumlu değildir.  
  
##  <a name="removeall"></a>  CArray::RemoveAll  
 Bu dizisinden tüm öğeleri kaldırır.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dizi zaten boşsa, işlev hala çalışmaktadır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#31](../../mfc/codesnippet/cpp/carray-class_11.cpp)]  
  
##  <a name="removeat"></a>  CArray::RemoveAt  
 Dizideki belirli bir dizinden başlayarak bir veya daha fazla öğeleri kaldırır.  
  
```  
void RemoveAt(
    INT_PTR nIndex,  
    INT_PTR nCount = 1);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Büyük veya 0 değerine eşit bir tamsayı dizini ve tarafından döndürülen değer eşit veya daha az [GetUpperBound](#getupperbound).  
  
 `nCount`  
 Kaldırılacak öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlem sırasında kaldırılan öğe yukarıdaki tüm öğeleri aşağı kaydırır. Bu üst dizisi bağlı ancak belleği serbest değil azaltır.  
  
 Dizideki kaldırma noktası yukarıda yer alan çok daha fazla öğe kaldırmayı deneyin, hata ayıklama sürümü kitaplığının onaylar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#32](../../mfc/codesnippet/cpp/carray-class_12.cpp)]  
  
##  <a name="setat"></a>  CArray::SetAt  
 Dizi öğesi belirtilen dizindeki ayarlar.  
  
```  
void SetAt(INT_PTR nIndex, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Büyük veya 0 değerine eşit bir tamsayı dizini ve tarafından döndürülen değer eşit veya daha az [GetUpperBound](#getupperbound).  
  
 `ARG_TYPE`  
 Dizi öğeleri başvurmak için kullanılan bağımsız türünü belirten bir şablon parametre.  
  
 `newElement`  
 Belirtilen konumda depolanması için yeni öğe değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 `SetAt` dizi büyümesine neden. Kullanım [SetAtGrow](#setatgrow) otomatik olarak büyümeye dizi istiyorsanız.  
  
 Dizin değeri geçerli bir konum dizideki temsil ettiğini emin olmalısınız. Sınırların dışında olması durumunda kitaplığının hata ayıklama sürümü onaylar.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [GetAt](#getat).  
  
##  <a name="setatgrow"></a>  CArray::SetAtGrow  
 Dizi öğesi belirtilen dizindeki ayarlar.  
  
```  
void SetAtGrow(INT_PTR nIndex, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Büyük veya 0 değerine eşit bir tamsayı dizini.  
  
 `ARG_TYPE`  
 Dizideki öğelerin türünü belirten bir şablon parametre.  
  
 `newElement`  
 Bu diziye eklenecek öğe. A **NULL** değerine izin verilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Gerekirse, dizi büyür (diğer bir deyişle, üst sınır yeni öğe uyum sağlayacak şekilde ayarlanır).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#33](../../mfc/codesnippet/cpp/carray-class_13.cpp)]  
  
##  <a name="setsize"></a>  CArray::SetSize  
 Boş veya varolan bir dizide boyutunu belirler; Gerekirse, bellek ayırır.  
  
```  
void SetSize(
    INT_PTR nNewSize,  
    INT_PTR nGrowBy = -1);
```  
  
### <a name="parameters"></a>Parametreler  
 `nNewSize`  
 Yeni dizi boyutu (öğelerin sayısı). Büyük veya 0 değerine eşit olmalıdır.  
  
 `nGrowBy`  
 Öğe yuva boyutu artışı gerekliyse ayırmak için minimum sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni boyutu eski boyutundan daha küçükse, dizi kesilir ve tüm kullanılmayan belleği serbest bırakılır.  
  
 Dizi kullanmaya başlamadan önce dizinin boyutunu ayarlamak için bu işlevi kullanın. Kullanmıyorsanız, `SetSize`, dizinizi için öğe eklemek görüntülenmesine neden olur sık bırakılan ve kopyalanır. Sık sık yeniden ayırma ve kopyalama verimsiz ve bellek parçalara.  
  
 `nGrowBy` Parametre dizisi artan sırada iç bellek ayırma etkiler. Kullanımı hiçbir zaman tarafından bildirilen dizi boyutu etkiler [GetSize](#getsize) ve [GetUpperBound](#getupperbound). Varsayılan değer kullanılırsa, MFC Bellek parçalanması önlemek ve verimliliği çoğu zaman için en iyi duruma getirmek için hesaplanan bir şekilde bellek ayırır.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [GetData](#getdata).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek Topla](../../visual-cpp-samples.md)   
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CObArray sınıfı](../../mfc/reference/cobarray-class.md)   
 [Koleksiyon Sınıfı Yardımcıları](../../mfc/reference/collection-class-helpers.md)
