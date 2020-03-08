---
title: CArray sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: f82dbf7dce2e14bf760bb76d23d23f667797ee0f
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78874517"
---
# <a name="carray-class"></a>CArray sınıfı

C dizileri gibi dizileri destekler, ancak gerektiğinde dinamik olarak azalabilir ve büyüyebilir.

## <a name="syntax"></a>Sözdizimi

```
template <class TYPE, class ARG_TYPE = const TYPE&>
class CArray : public CObject
```

#### <a name="parameters"></a>Parametreler

*TÜRÜYLE*<br/>
Dizide depolanan nesne türünü belirten şablon parametresi. *Tür* , `CArray`tarafından döndürülen bir parametredir.

*ARG_TYPE*<br/>
Dizide depolanan nesnelere erişmek için kullanılan bağımsız değişken türünü belirten şablon parametresi. Genellikle *türe*bir başvuru. *ARG_TYPE* , `CArray`geçirilen bir parametredir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CArray:: CArray](#carray)|Boş bir dizi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CArray:: Add](#add)|Dizinin sonuna bir öğesi ekler; gerekirse diziyi büyür.|
|[CArray:: Append](#append)|Diziye başka bir dizi ekler; gerekirse diziyi büyür|
|[CArray:: Copy](#copy)|Başka bir diziyi diziye kopyalar; gerekirse diziyi büyür.|
|[CArray:: ElementAt](#elementat)|Dizi içindeki öğe işaretçisine geçici bir başvuru döndürür.|
|[CArray:: FreeExtra](#freeextra)|Geçerli üst sınırın üzerinde kullanılmayan tüm belleği serbest bırakır.|
|[CArray:: GetAt](#getat)|Verilen dizindeki değeri döndürür.|
|[CArray:: GetCount](#getcount)|Bu dizideki öğelerin sayısını alır.|
|[CArray:: GetData](#getdata)|Dizideki öğelere erişime izin verir. NULL olabilir.|
|[CArray:: GetSize](#getsize)|Bu dizideki öğelerin sayısını alır.|
|[CArray:: Getüstebağı](#getupperbound)|En büyük geçerli dizini döndürür.|
|[CArray:: InsertAt](#insertat)|Belirtilen dizine bir öğe (veya başka bir dizide bulunan tüm öğeleri) ekler.|
|[CArray:: IsEmpty](#isempty)|Dizinin boş olup olmadığını belirler.|
|[CArray:: RemoveAll](#removeall)|Bu dizideki tüm öğeleri kaldırır.|
|[CArray:: RemoveAt](#removeat)|Belirli bir dizindeki bir öğeyi kaldırır.|
|[CArray:: SetAt](#setat)|Belirli bir dizin için değeri ayarlar; dizinin büyümesine izin verilmiyor.|
|[CArray:: SetAtGrow](#setatgrow)|Belirli bir dizin için değeri ayarlar; gerekirse diziyi büyür.|
|[CArray:: SetSize](#setsize)|Bu dizide yer alan öğelerin sayısını ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[işlecinde&#91;&#93;](#operator_at)|Belirtilen dizindeki öğeyi ayarlar veya alır.|

## <a name="remarks"></a>Açıklamalar

Dizi dizinleri her zaman 0 konumunda başlar. Üst sınırı düzeltireceğinize karar verebilir veya geçerli sınırı aşan öğeleri eklediğinizde bu dizinin genişlemesine izin verebilirsiniz. Bitişik olarak, bazı öğeler null olsa bile üst sınır için ayrılır.

> [!NOTE]
>  `CArray` nesnesini yeniden boyutlandırma veya öğe ekleme yöntemleri, öğeleri taşımak için [memcpy_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md) kullanır. Bu bir sorundur çünkü `memcpy_s` oluşturucunun çağrılması gereken nesnelerle uyumlu değildir. `CArray` öğeler `memcpy_s`uyumlu değilse, uygun boyutun yeni bir `CArray` oluşturmanız gerekir. Ardından, bu yöntemler `memcpy_s`yerine bir atama işleci kullandığından yeni diziyi doldurmak için [CArray:: Copy](#copy) ve [CArray:: SetAt](#setat) ' i kullanmanız gerekir.

C dizisinde olduğu gibi, `CArray` dizinli bir öğe için erişim süresi sabittir ve dizi boyutundan bağımsızdır.

> [!TIP]
>  Bir Array kullanmadan önce, boyutunu belirlemek ve için bellek ayırmak üzere [SetSize](#setsize) kullanın. `SetSize`kullanmıyorsanız, dizine öğe eklemek, bu öğenin sık olarak yeniden tahsis edilmesine ve kopyalanmasına neden olur. Sık yeniden ayırma ve kopyalama verimsiz ve bellek parçalara ayırma yapılabilir.

Bir dizideki tek tek öğelerin dökümünden birine ihtiyacınız varsa, [CDumpContext](../../mfc/reference/cdumpcontext-class.md) nesnesinin derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

Bu sınıfın bazı üye işlevleri, `CArray` sınıfının çoğu kullanımları için özelleştirilmek zorunda olan genel yardımcı işlevleri çağırır. MFC makroları ve Genel bölümünde [koleksiyon sınıfı Yardımcıları](../../mfc/reference/collection-class-helpers.md) konusuna bakın.

Dizi sınıfı türetme, liste türetmeye benzer.

`CArray`kullanma hakkında daha fazla bilgi için, bkz. Makale [koleksiyonları](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CArray`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtempl. h

##  <a name="add"></a>CArray:: Add

Dizinin sonuna yeni bir öğe ekler ve diziyi 1 artırır.

```
INT_PTR Add(ARG_TYPE newElement);
```

### <a name="parameters"></a>Parametreler

*ARG_TYPE*<br/>
Bu dizideki öğelere başvuran bağımsız değişkenlerin türünü belirten şablon parametresi.

*newElement*<br/>
Bu diziye eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

Eklenen öğenin dizini.

### <a name="remarks"></a>Açıklamalar

[SetSize](#setsize) değeri 1 ' den büyük bir `nGrowBy` değerle kullanılmışsa, ek bellek ayrılabilir. Ancak, üst sınır yalnızca 1 ' i arttırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#22](../../mfc/codesnippet/cpp/carray-class_1.cpp)]

##  <a name="append"></a>CArray:: Append

Bir dizinin içeriğini diğerinin sonuna eklemek için bu üye işlevini çağırın.

```
INT_PTR Append(const CArray& src);
```

### <a name="parameters"></a>Parametreler

*YN*<br/>
Bir diziye eklenecek öğelerin kaynağı.

### <a name="return-value"></a>Dönüş Değeri

İlk eklenen öğenin dizini.

### <a name="remarks"></a>Açıklamalar

Diziler aynı türde olmalıdır.

Gerekirse, `Append` diziye eklenen öğeleri karşılamak için ek bellek ayırabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#23](../../mfc/codesnippet/cpp/carray-class_2.cpp)]

##  <a name="carray"></a>CArray:: CArray

Boş bir dizi oluşturur.

```
CArray();
```

### <a name="remarks"></a>Açıklamalar

Dizi tek seferde bir öğeyi büyürken.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#24](../../mfc/codesnippet/cpp/carray-class_3.cpp)]

##  <a name="copy"></a>CArray:: Copy

Bir dizinin öğelerini diğerine kopyalamak için bu üye işlevini kullanın.

```
void Copy(const CArray& src);
```

### <a name="parameters"></a>Parametreler

*YN*<br/>
Bir diziye kopyalanacak öğelerin kaynağı.

### <a name="remarks"></a>Açıklamalar

Başka bir dizinin öğeleriyle bir dizinin öğelerinin üzerine yazmak için bu üye işlevi çağırın.

`Copy` belleği serbest vermez; Ancak, gerekirse diziye kopyalanmış öğeleri karşılamak için `Copy` ek bellek ayırabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#25](../../mfc/codesnippet/cpp/carray-class_4.cpp)]

##  <a name="elementat"></a>CArray:: ElementAt

Dizi içinde belirtilen öğeye geçici bir başvuru döndürür.

```
TYPE& ElementAt(INT_PTR nIndex);
const TYPE& ElementAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
0 ' dan büyük veya buna eşit ve [Getüstsınırı](#getupperbound)tarafından döndürülen değerden küçük ya da buna eşit bir tamsayı dizini.

### <a name="return-value"></a>Dönüş Değeri

Bir dizi öğesine başvuru.

### <a name="remarks"></a>Açıklamalar

Diziler için sol taraftaki atama işlecini uygulamak için kullanılır.

### <a name="example"></a>Örnek

  [GetSize](#getsize)örneğine bakın.

##  <a name="freeextra"></a>CArray:: FreeExtra

Dizi büyüirken ayrılan ek belleği serbest bırakır.

```
void FreeExtra();
```

### <a name="remarks"></a>Açıklamalar

Bu işlevin, dizinin boyutu veya üst sınırı üzerinde hiçbir etkisi yoktur.

### <a name="example"></a>Örnek

  [GetData](#getdata)örneğine bakın.

##  <a name="getat"></a>CArray:: GetAt

Belirtilen dizindeki dizi öğesini döndürür.

```
TYPE& GetAt(INT_PTR nIndex);
const TYPE& GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Parametreler

*TÜRÜYLE*<br/>
Dizi öğelerinin türünü belirten şablon parametresi.

*nDizin*<br/>
0 ' dan büyük veya buna eşit ve [Getüstsınırı](#getupperbound)tarafından döndürülen değerden küçük ya da buna eşit bir tamsayı dizini.

### <a name="return-value"></a>Dönüş Değeri

Şu anda bu dizinde bulunan Array öğesi.

### <a name="remarks"></a>Açıklamalar

Negatif bir değer veya `GetUpperBound` tarafından döndürülen değerden daha büyük bir değer geçirilmesi, başarısız bir onaylama işlemi oluşmasına neden olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#26](../../mfc/codesnippet/cpp/carray-class_5.cpp)]

##  <a name="getcount"></a>CArray:: GetCount

Dizi öğelerinin sayısını döndürür.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizideki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Dizideki öğe sayısını almak için bu yöntemi çağırın. Dizinler sıfır tabanlı olduğundan, boyut en büyük dizinden 1 büyük olur. Bu yöntemin çağrılması, [CArray:: GetSize](#getsize) yöntemiyle aynı sonucu oluşturacaktır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#27](../../mfc/codesnippet/cpp/carray-class_6.cpp)]

##  <a name="getdata"></a>CArray:: GetData

Bir dizideki öğelere doğrudan erişim kazanmak için bu üye işlevini kullanın.

```
const TYPE* GetData() const;
TYPE* GetData();
```

### <a name="parameters"></a>Parametreler

*TÜRÜYLE*<br/>
Dizi öğelerinin türünü belirten şablon parametresi.

### <a name="return-value"></a>Dönüş Değeri

Dizi öğesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Kullanılabilir öğe yoksa `GetData` null değer döndürür.

Bir dizinin öğelerine doğrudan erişim daha hızlı çalışmanıza yardımcı olmakla birlikte `GetData`çağırırken dikkatli bir şekilde yararlanabilirsiniz; yaptığınız tüm hatalar dizinizdeki öğeleri doğrudan etkiler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#28](../../mfc/codesnippet/cpp/carray-class_7.cpp)]

##  <a name="getsize"></a>CArray:: GetSize

Dizinin boyutunu döndürür.

```
INT_PTR GetSize() const;
```

### <a name="remarks"></a>Açıklamalar

Dizinler sıfır tabanlı olduğundan, boyut en büyük dizinden 1 büyük olur. Bu yöntemin çağrılması, [CArray:: GetCount](#getcount) yöntemiyle aynı sonucu oluşturacaktır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#29](../../mfc/codesnippet/cpp/carray-class_8.cpp)]

##  <a name="getupperbound"></a>CArray:: Getüstebağı

Bu dizinin geçerli üst sınırını döndürür.

```
INT_PTR GetUpperBound() const;
```

### <a name="remarks"></a>Açıklamalar

Dizi dizinleri sıfır tabanlı olduğundan, bu işlev `GetSize`1 ' den küçük bir değer döndürür.

`GetUpperBound( )` =-1 koşulu, dizinin hiçbir öğe içermediğini belirtir.

### <a name="example"></a>Örnek

  [CArray:: GetAt](#getat)örneğine bakın.

##  <a name="insertat"></a>CArray:: InsertAt

`InsertAt` ilk sürümü bir dizide belirtilen bir dizine bir öğe (veya bir öğenin birden çok kopyasını) ekler.

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

*nDizin*<br/>
`GetUpperBound`tarafından döndürülen değerden daha büyük olabilecek bir tamsayı dizini.

*ARG_TYPE*<br/>
Bu dizideki öğelerin türünü belirten şablon parametresi.

*newElement*<br/>
Bu diziye yerleştirilecek öğe.

*nCount*<br/>
Bu öğenin Eklenme sayısı (varsayılan 1 ' dir).

*nStartIndex*<br/>
[Getüstsınırı](#getupperbound)tarafından döndürülen değerden daha büyük olabilecek bir tamsayı dizini.

*pNewArray*<br/>
Bu diziye eklenecek öğeleri içeren başka bir dizi.

### <a name="remarks"></a>Açıklamalar

İşlemde, (dizini arttırarak) Bu dizindeki mevcut öğeyi yukarı kaydırır ve yukarıdaki tüm öğeleri kaydırır.

İkinci sürüm, *nStartIndex* konumundan başlayarak başka bir `CArray` koleksiyonundan tüm öğeleri ekler.

Buna karşılık `SetAt` işlevi, belirtilen bir dizi öğesinin yerini alır ve herhangi bir öğeyi kaydıramaz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#30](../../mfc/codesnippet/cpp/carray-class_9.cpp)]

##  <a name="isempty"></a>CArray:: IsEmpty

Dizinin boş olup olmadığını belirler.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizi hiçbir öğe içermiyorsa sıfır dışı; Aksi takdirde 0.

##  <a name="operator_at"></a>CArray:: operator \[\]

Bu alt simge işleçleri, [SetAt](#setat) ve [GetAt](#getat) işlevlerinin kullanışlı bir yerleridir.

```
TYPE& operator[](int_ptr nindex);
const TYPE& operator[](int_ptr nindex) const;
```

### <a name="parameters"></a>Parametreler

*TÜRÜYLE*<br/>
Bu dizideki öğelerin türünü belirten şablon parametresi.

*nDizin*<br/>
Erişilecek öğenin dizini.

### <a name="remarks"></a>Açıklamalar

**Const**olmayan diziler için çağrılan ilk operatör, atama ifadesinin sağ (r-value) veya Left (l-value) üzerinde kullanılabilir. **Const** dizileri için çağrılan ikinci, yalnızca sağda kullanılabilir.

Kitaplığın hata ayıklama sürümü, alt simge (atama ifadesinin solunda ya da sağ tarafında) sınırların dışında olup olmadığını onaylar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#34](../../mfc/codesnippet/cpp/carray-class_10.cpp)]

##  <a name="relocateelements"></a>CArray:: Relocateöğeleri

Dizinin büyümesi veya küçültülmesi gerektiğinde verileri yeni bir arabelleğe yeniden konumlandırır.

```
template<class TYPE, class ARG_TYPE>
AFX_INLINE void CArray<TYPE, ARG_TYPE>::RelocateElements(
    TYPE* pNewData,
    const TYPE* pData,
    INT_PTR nCount);
```

### <a name="parameters"></a>Parametreler

*pNewData*<br/>
Öğe dizisi için yeni bir arabellek.

*pData*<br/>
Eski öğe dizisi.

*nCount*<br/>
Eski dizideki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

*Pnewdata* her zaman tüm *pData* öğelerini tutabilecek kadar büyük.

[CArray](../../mfc/reference/carray-class.md) uygulamasının, dizinin büyümesi veya küçültülmesi gerektiğinde ( [SetSize](#setsize) veya [FreeExtra](#freeextra) çağrıldığında) eski verileri yeni bir arabelleğe kopyalamak için bu yöntemi kullanır. Varsayılan uygulama yalnızca verileri kopyalar.

Bir öğenin kendi üyelerinden birine yönelik bir işaretçi içerdiği diziler veya başka bir yapı dizi öğelerinden birine yönelik bir işaretçi içeriyorsa, işaretçiler düz kopyada güncellenmez. Bu durumda, ilgili türler ile `RelocateElements` özelleştirmesi uygulayarak işaretçileri düzeltebilirsiniz. Verilerin kopyalanmasından de sorumlu olursunuz.

##  <a name="removeall"></a>CArray:: RemoveAll

Bu dizideki tüm öğeleri kaldırır.

```
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

Dizi zaten boşsa, işlev hala çalışır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#31](../../mfc/codesnippet/cpp/carray-class_11.cpp)]

##  <a name="removeat"></a>CArray:: RemoveAt

Bir dizide belirtilen dizinden başlayarak bir veya daha fazla öğeyi kaldırır.

```
void RemoveAt(
    INT_PTR nIndex,
    INT_PTR nCount = 1);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
0 ' dan büyük veya buna eşit ve [Getüstsınırı](#getupperbound)tarafından döndürülen değerden küçük ya da buna eşit bir tamsayı dizini.

*nCount*<br/>
Kaldırılacak öğe sayısı.

### <a name="remarks"></a>Açıklamalar

İşlemde, kaldırılan öğelerin üzerindeki tüm öğeleri aşağı kaydırır. Dizinin üst sınırını azaltır, ancak belleği serbest vermez.

Kaldırma noktasının üzerindeki dizide yer alan daha fazla öğeyi kaldırmaya çalışırsanız, kitaplığın hata ayıklama sürümü onaylar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#32](../../mfc/codesnippet/cpp/carray-class_12.cpp)]

##  <a name="setat"></a>CArray:: SetAt

Belirtilen dizinde dizi öğesini ayarlar.

```
void SetAt(INT_PTR nIndex, ARG_TYPE newElement);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
0 ' dan büyük veya buna eşit ve [Getüstsınırı](#getupperbound)tarafından döndürülen değerden küçük ya da buna eşit bir tamsayı dizini.

*ARG_TYPE*<br/>
Dizi öğelerine başvurmak için kullanılan bağımsız değişkenlerin türünü belirten şablon parametresi.

*newElement*<br/>
Belirtilen konumda depolanacak yeni öğe değeri.

### <a name="remarks"></a>Açıklamalar

`SetAt`, dizinin büyümesine neden olmaz. Dizinin otomatik olarak büyümesini istiyorsanız [SetAtGrow](#setatgrow) kullanın.

Dizin değerinin dizideki geçerli bir konumu temsil ettiğinden emin olmanız gerekir. Sınırların dışında ise, kitaplığın hata ayıklama sürümü onaylar.

### <a name="example"></a>Örnek

  [GetAt](#getat)için örneğe bakın.

##  <a name="setatgrow"></a>CArray:: SetAtGrow

Belirtilen dizinde dizi öğesini ayarlar.

```
void SetAtGrow(INT_PTR nIndex, ARG_TYPE newElement);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
0 ' dan büyük veya buna eşit bir tamsayı dizini.

*ARG_TYPE*<br/>
Dizideki öğelerin türünü belirten şablon parametresi.

*newElement*<br/>
Bu diziye eklenecek öğe. NULL değere izin verilir.

### <a name="remarks"></a>Açıklamalar

Dizi gerektiğinde otomatik olarak büyür (yani, üst sınır yeni öğeye uyum sağlayacak şekilde ayarlanır).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#33](../../mfc/codesnippet/cpp/carray-class_13.cpp)]

##  <a name="setsize"></a>CArray:: SetSize

Boş veya mevcut bir dizinin boyutunu oluşturur; gerekirse belleği ayırır.

```
void SetSize(
    INT_PTR nNewSize,
    INT_PTR nGrowBy = -1);
```

### <a name="parameters"></a>Parametreler

*nNewSize*<br/>
Yeni dizi boyutu (öğe sayısı). 0 ' dan büyük veya buna eşit olmalıdır.

*nGrowBy*<br/>
Boyut artışı gerekliyse ayrılacak en az öğe yuvası sayısı.

### <a name="remarks"></a>Açıklamalar

Yeni boyut eski boyuttan küçükse, dizi kesilir ve kullanılmayan tüm bellek serbest bırakılır.

Diziyi kullanmaya başlamadan önce dizinizin boyutunu ayarlamak için bu işlevi kullanın. `SetSize`kullanmıyorsanız, dizine öğe eklemek, bu öğenin sık olarak yeniden tahsis edilmesine ve kopyalanmasına neden olur. Sık yeniden ayırma ve kopyalama verimsiz ve bellek parçalara ayırma yapılabilir.

*NGrowBy* parametresi, dizi büyüirken iç bellek ayırmayı etkiler. Kullanımı, [GetSize](#getsize) ve [getüstsınırı](#getupperbound)tarafından bildirilen dizi boyutunu hiçbir şekilde etkilemez. Varsayılan değer kullanılırsa, MFC bellek parçalanmasını önlemek ve çoğu durumda verimliliği iyileştirmek için bir şekilde bellek ayırır.

### <a name="example"></a>Örnek

  [GetData](#getdata)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek toplama](../../overview/visual-cpp-samples.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CObArray Sınıfı](../../mfc/reference/cobarray-class.md)<br/>
[Koleksiyon Sınıfı Yardımcıları](../../mfc/reference/collection-class-helpers.md)
