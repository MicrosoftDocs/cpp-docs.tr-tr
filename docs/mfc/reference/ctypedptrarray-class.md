---
title: CTypedPtrArray Sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 20cf147e955b6b19919f35750b0f46a8b5a67ad0
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752068"
---
# <a name="ctypedptrarray-class"></a>CTypedPtrArray Sınıfı

Sınıf `CPtrArray` veya `CObArray`nesneler için tür güvenli bir "sarmalayıcı" sağlar.

## <a name="syntax"></a>Sözdizimi

```
template<class BASE_CLASS, class TYPE>
class CTypedPtrArray : public BASE_CLASS
```

#### <a name="parameters"></a>Parametreler

*BASE_CLASS*<br/>
Daktio işaretçi dizi sınıfının taban sınıfı; bir dizi sınıfı `CObArray` olmalıdır `CPtrArray`( veya ).

*TÜR*<br/>
Taban sınıf dizisinde depolanan öğelerin türü.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CTypedPtrArray::Ekle](#add)|Dizinin sonuna yeni bir öğe ekler. Gerekirse diziyi büyütür|
|[CTypedPtrArray::Ek](#append)|Bir dizinin içeriğini diğerinin sonuna ekler. Gerekirse diziyi büyütür|
|[CTypedPtrArray::Kopyala](#copy)|Başka bir diziyi diziye kopyalar; gerekirse diziyi büyütür.|
|[CTypedPtrArray::ElementAt](#elementat)|Dizi içindeki öğe işaretçisine geçici bir başvuru verir.|
|[CTypedPtrArray::GetAt](#getat)|Belirli bir dizindeki değeri döndürür.|
|[CTypedPtrArray::InsertAt](#insertat)|Belirli bir dizide bir öğe (veya başka bir dizideki tüm öğeler) ekler.|
|[CTypedPtrArray::SetAt](#setat)|Belirli bir dizinin değerini ayarlar; dizi büyümeye izin verilmez.|
|[CTypedPtrArray::SetAtGrow](#setatgrow)|Belirli bir dizinin değerini ayarlar; gerekirse diziyi büyütür.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CTypedPtrArray::operatör \[\]](#operator_at)|Belirtilen dizilişte öğeyi ayarlar veya alır.|

## <a name="remarks"></a>Açıklamalar

C++ `CTypedPtrArray` yazı `CPtrArray` denetimi `CObArray`tesisi yerine veya yerine kullandığınızda, eşleşmeyan işaretçi türlerinin neden olduğu hataların giderilmesine yardımcı olur.

Buna ek `CTypedPtrArray` olarak, sarıcı kullandıysanız `CObArray` veya `CPtrArray`gerekli olacak döküm çok gerçekleştirir.

Tüm `CTypedPtrArray` işlevler satır lı olduğundan, bu şablonun kullanımı kodunuzun boyutunu veya hızını önemli ölçüde etkilemez.

Kullanma `CTypedPtrArray`hakkında daha fazla bilgi için [Koleksiyonlar](../../mfc/collections.md) ve [Şablon Tabanlı Sınıflar](../../mfc/template-based-classes.md)makalelerine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`BASE_CLASS`

`CTypedPtrArray`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxtempl.h

## <a name="ctypedptrarrayadd"></a><a name="add"></a>CTypedPtrArray::Ekle

Bu üye `BASE_CLASS`işlev **::Ekle**.

```
INT_PTR Add(TYPE newElement);
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Diziye eklenecek öğe türünü belirten şablon parametresi.

*newElement*<br/>
Bu diziye eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

Eklenen öğenin dizin.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için [Bkz. CObArray::Ekle](../../mfc/reference/cobarray-class.md#add).

## <a name="ctypedptrarrayappend"></a><a name="append"></a>CTypedPtrArray::Ek

Bu üye `BASE_CLASS`işlev ::Ek**' yi çağırır.

```
INT_PTR Append(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```

### <a name="parameters"></a>Parametreler

*BASE_CLASS*<br/>
Daktio işaretçi dizi sınıfının taban sınıfı; bir dizi sınıfı [(CObArray](../../mfc/reference/cobarray-class.md) veya [CPtrArray)](../../mfc/reference/cptrarray-class.md)olmalıdır.

*TÜR*<br/>
Taban sınıf dizisinde depolanan öğelerin türü.

*src*<br/>
Bir diziye eklenecek öğelerin kaynağı.

### <a name="return-value"></a>Dönüş Değeri

İlk eklenen öğenin dizini.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için [CObArray::Append'e](../../mfc/reference/cobarray-class.md#append)bakın.

## <a name="ctypedptrarraycopy"></a><a name="copy"></a>CTypedPtrArray::Kopyala

Bu üye `BASE_CLASS`işlev **::Kopyala**.

```cpp
void Copy(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```

### <a name="parameters"></a>Parametreler

*BASE_CLASS*<br/>
Daktio işaretçi dizi sınıfının taban sınıfı; bir dizi sınıfı [(CObArray](../../mfc/reference/cobarray-class.md) veya [CPtrArray)](../../mfc/reference/cptrarray-class.md)olmalıdır.

*TÜR*<br/>
Taban sınıf dizisinde depolanan öğelerin türü.

*src*<br/>
Bir diziye kopyalanacak öğelerin kaynağı.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için [Bkz. CObArray::Kopyala.](../../mfc/reference/cobarray-class.md#copy)

## <a name="ctypedptrarrayelementat"></a><a name="elementat"></a>CTypedPtrArray::ElementAt

Bu satır satırlı fonksiyon çağırır `BASE_CLASS` **::ElementAt**.

```
TYPE& ElementAt(INT_PTR nIndex);
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Bu dizide depolanan öğelerin türünü belirten şablon parametresi.

*Nındex*<br/>
0'dan büyük veya eşit ve `BASE_CLASS` **"GetUpperBound**" tarafından döndürülen değerden daha az veya eşit olan bir tümseci dizini.

### <a name="return-value"></a>Dönüş Değeri

*nIndex*tarafından belirtilen konumdaki öğeye geçici bir başvuru. Bu öğe şablon parametre *TYPE*tarafından belirtilen tür .

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için [CObArray::ElementAt'](../../mfc/reference/cobarray-class.md#elementat)a bakın.

## <a name="ctypedptrarraygetat"></a><a name="getat"></a>CTypedPtrArray::GetAt

Bu satır satırlı fonksiyon çağırır `BASE_CLASS` **::GetAt**.

```
TYPE GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Dizide depolanan öğelerin türünü belirten şablon parametresi.

*Nındex*<br/>
0'dan büyük veya eşit ve `BASE_CLASS` **"GetUpperBound**" tarafından döndürülen değerden daha az veya eşit olan bir tümseci dizini.

### <a name="return-value"></a>Dönüş Değeri

*nIndex*tarafından belirtilen konumdaki öğenin bir kopyası. Bu öğe şablon parametre *TYPE*tarafından belirtilen tür .

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için [Bkz. CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)

## <a name="ctypedptrarrayinsertat"></a><a name="insertat"></a>CTypedPtrArray::InsertAt

Bu üye `BASE_CLASS`işlev **::InsertAt**.

```cpp
void InsertAt(
    INT_PTR nIndex,
    TYPE newElement,
    INT_PTR nCount = 1);

void InsertAt(
    INT_PTR nStartIndex,
    CTypedPtrArray<BASE_CLASS, TYPE>* pNewArray);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
CObArray tarafından döndürülen değerden daha büyük olabilecek bir sonsayı [dizini::GetUpperBound.](../../mfc/reference/cobarray-class.md#getupperbound)

*TÜR*<br/>
Taban sınıf dizisinde depolanan öğelerin türü.

*newElement*<br/>
Bu diziye yerleştirilecek nesne işaretçisi. Null **değerinin** yeni bir *öğesine* izin verilir.

*nSayısı*<br/>
Bu öğenin kaç kez eklenmesi gerekir (varsayılan olarak 1).

*nBaşlangıç Endeksi*<br/>
Tarafından döndürülen değerden büyük olabilecek bir `CObArray::GetUpperBound`karşılayon dizini.

*BASE_CLASS*<br/>
Daktio işaretçi dizi sınıfının taban sınıfı; bir dizi sınıfı [(CObArray](../../mfc/reference/cobarray-class.md) veya [CPtrArray)](../../mfc/reference/cptrarray-class.md)olmalıdır.

*pNewArray*<br/>
Bu diziye eklenecek öğeleri içeren başka bir dizi.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için [CObArray::InsertAt'](../../mfc/reference/cobarray-class.md#insertat)a bakın.

## <a name="ctypedptrarrayoperator--"></a><a name="operator_at"></a>CTypedPtrArray::operatör [ ]

Bu satırlı `BASE_CLASS`işleçler **::operator [ ]** diyoruz.

```
TYPE& operator[ ](int_ptr nindex);
TYPE operator[ ](int_ptr nindex) const;
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Dizide depolanan öğelerin türünü belirten şablon parametresi.

*Nındex*<br/>
0'dan büyük veya eşit ve `BASE_CLASS` **"GetUpperBound**" tarafından döndürülen değerden daha az veya eşit olan bir tümseci dizini.

### <a name="remarks"></a>Açıklamalar

**Const**olmayan diziler için çağrılan ilk işleç, atama deyiminin sağında (r değeri) veya sol (l-değeri) kullanılabilir. Const diziler **const** için çağrılan ikinci, yalnızca sağda kullanılabilir.

Kitaplığın Hata Ayıklama sürümü, alt yazının (atama deyiminin solunda veya sağ tarafında) sınırların dışında olduğunu ileri sürer.

## <a name="ctypedptrarraysetat"></a><a name="setat"></a>CTypedPtrArray::SetAt

Bu üye `BASE_CLASS`işlev **::SetAt.**

```cpp
void SetAt(
    INT_PTR nIndex,
    TYPE ptr);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
0'dan büyük veya eşit ve CObArray tarafından döndürülen değerden daha az veya eşit olan bir sonsayı [dizini::GetUpperBound.](../../mfc/reference/cobarray-class.md#getupperbound)

*TÜR*<br/>
Taban sınıf dizisinde depolanan öğelerin türü.

*Ptr*<br/>
nIndex'teki diziye eklenecek öğeiçin bir işaretçi. NULL değerine izin verilir.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için [CObArray::SetAt'a](../../mfc/reference/cobarray-class.md#setat)bakın.

## <a name="ctypedptrarraysetatgrow"></a><a name="setatgrow"></a>CTypedPtrArray::SetAtGrow

Bu üye `BASE_CLASS`işlev **::SetAtGrow**.

```cpp
void SetAtGrow(
    INT_PTR nIndex,
    TYPE newElement);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
0'dan büyük veya eşit bir sonsayı dizini.

*TÜR*<br/>
Taban sınıf dizisinde depolanan öğelerin türü.

*newElement*<br/>
Bu diziye eklenecek nesne işaretçisi. **NULL** değerine izin verilir.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için [CObArray::SetAtGrow'](../../mfc/reference/cobarray-class.md#setatgrow)a bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek TOPLAMA](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CPtrArray Sınıfı](../../mfc/reference/cptrarray-class.md)<br/>
[CObArray Sınıfı](../../mfc/reference/cobarray-class.md)
