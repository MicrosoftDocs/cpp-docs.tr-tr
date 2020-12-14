---
description: 'Daha fazla bilgi edinin: CTypedPtrArray sınıfı'
title: CTypedPtrArray sınıfı
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
ms.openlocfilehash: 07d254072a51a56759a3dbe569c36ff65d199cfe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345010"
---
# <a name="ctypedptrarray-class"></a>CTypedPtrArray sınıfı

, Veya sınıfının nesneleri için tür açısından güvenli bir "sarmalayıcı" `CPtrArray` sağlar `CObArray` .

## <a name="syntax"></a>Sözdizimi

```
template<class BASE_CLASS, class TYPE>
class CTypedPtrArray : public BASE_CLASS
```

#### <a name="parameters"></a>Parametreler

*BASE_CLASS*<br/>
Türü belirtilmiş işaretçi dizisi sınıfının temel sınıfı; bir dizi sınıfı ( `CObArray` veya) olmalıdır `CPtrArray` .

*TÜR*<br/>
Temel sınıf dizide depolanan öğelerin türü.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CTypedPtrArray:: Add](#add)|Dizinin sonuna yeni bir öğe ekler. Gerekirse diziyi büyür|
|[CTypedPtrArray:: Append](#append)|Bir dizinin içeriğini diğerinin sonuna ekler. Gerekirse diziyi büyür|
|[CTypedPtrArray:: Copy](#copy)|Başka bir diziyi diziye kopyalar; gerekirse diziyi büyür.|
|[CTypedPtrArray:: ElementAt](#elementat)|Dizi içindeki öğe işaretçisine geçici bir başvuru döndürür.|
|[CTypedPtrArray:: GetAt](#getat)|Verilen dizindeki değeri döndürür.|
|[CTypedPtrArray:: InsertAt](#insertat)|Belirtilen dizine bir öğe (veya başka bir dizide bulunan tüm öğeleri) ekler.|
|[CTypedPtrArray:: SetAt](#setat)|Belirli bir dizin için değeri ayarlar; dizinin büyümesine izin verilmiyor.|
|[CTypedPtrArray:: SetAtGrow](#setatgrow)|Belirli bir dizin için değeri ayarlar; gerekirse diziyi büyür.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CTypedPtrArray:: işleci \[\]](#operator_at)|Belirtilen dizindeki öğeyi ayarlar veya alır.|

## <a name="remarks"></a>Açıklamalar

`CTypedPtrArray`Ya da yerine kullandığınızda `CPtrArray` `CObArray` , C++ tür denetimi özelliği eşleşmeyen işaretçi türleri nedeniyle oluşan hataları ortadan kaldırmaya yardımcı olur.

Ayrıca `CTypedPtrArray` sarmalayıcı, veya kullandıysanız gerekli olacak çok sayıda atama gerçekleştirir `CObArray` `CPtrArray` .

Tüm `CTypedPtrArray` işlevler satır içi olduğundan, bu şablonun kullanımı kodunuzun boyutunu veya hızını önemli ölçüde etkilemez.

Kullanma hakkında daha fazla bilgi için `CTypedPtrArray` bkz. Makale [koleksiyonları](../../mfc/collections.md) ve [şablon tabanlı sınıflar](../../mfc/template-based-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`BASE_CLASS`

`CTypedPtrArray`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtempl. h

## <a name="ctypedptrarrayadd"></a><a name="add"></a> CTypedPtrArray:: Add

Bu üye işlevi `BASE_CLASS` **:: Add** öğesini çağırır.

```
INT_PTR Add(TYPE newElement);
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Diziye eklenecek öğenin türünü belirten şablon parametresi.

*newElement*<br/>
Bu diziye eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

Eklenen öğenin dizini.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için bkz. [CObArray:: Add](../../mfc/reference/cobarray-class.md#add).

## <a name="ctypedptrarrayappend"></a><a name="append"></a> CTypedPtrArray:: Append

Bu üye işlevi `BASE_CLASS` :: Append * * öğesini çağırır.

```
INT_PTR Append(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```

### <a name="parameters"></a>Parametreler

*BASE_CLASS*<br/>
Türü belirtilmiş işaretçi dizisi sınıfının temel sınıfı; bir dizi sınıfı ( [CObArray](../../mfc/reference/cobarray-class.md) veya [CPtrArray](../../mfc/reference/cptrarray-class.md)) olmalıdır.

*TÜR*<br/>
Temel sınıf dizide depolanan öğelerin türü.

*src*<br/>
Bir diziye eklenecek öğelerin kaynağı.

### <a name="return-value"></a>Dönüş Değeri

İlk eklenen öğenin dizini.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için bkz. [CObArray:: Append](../../mfc/reference/cobarray-class.md#append).

## <a name="ctypedptrarraycopy"></a><a name="copy"></a> CTypedPtrArray:: Copy

Bu üye işlevi `BASE_CLASS` **:: Copy** öğesini çağırır.

```cpp
void Copy(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```

### <a name="parameters"></a>Parametreler

*BASE_CLASS*<br/>
Türü belirtilmiş işaretçi dizisi sınıfının temel sınıfı; bir dizi sınıfı ( [CObArray](../../mfc/reference/cobarray-class.md) veya [CPtrArray](../../mfc/reference/cptrarray-class.md)) olmalıdır.

*TÜR*<br/>
Temel sınıf dizide depolanan öğelerin türü.

*src*<br/>
Bir diziye kopyalanacak öğelerin kaynağı.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için bkz. [CObArray:: Copy](../../mfc/reference/cobarray-class.md#copy).

## <a name="ctypedptrarrayelementat"></a><a name="elementat"></a> CTypedPtrArray:: ElementAt

Bu satır içi işlev `BASE_CLASS` **:: ElementAt** çağırır.

```
TYPE& ElementAt(INT_PTR nIndex);
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Bu dizide depolanan öğelerin türünü belirten şablon parametresi.

*nDizin*<br/>
0 ' dan büyük veya buna eşit ve `BASE_CLASS` **:: getüstelen** değerden küçük veya buna eşit bir tamsayı dizini.

### <a name="return-value"></a>Dönüş Değeri

*NIndex* tarafından belirtilen konumdaki öğeye geçici bir başvuru. Bu öğe, şablon parametre *türü* tarafından belirtilen türdür.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için bkz. [CObArray:: ElementAt](../../mfc/reference/cobarray-class.md#elementat).

## <a name="ctypedptrarraygetat"></a><a name="getat"></a> CTypedPtrArray:: GetAt

Bu satır içi işlev `BASE_CLASS` **:: GetAt** çağırır.

```
TYPE GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Dizide depolanan öğelerin türünü belirten şablon parametresi.

*nDizin*<br/>
0 ' dan büyük veya buna eşit ve `BASE_CLASS` **:: getüstelen** değerden küçük veya buna eşit bir tamsayı dizini.

### <a name="return-value"></a>Dönüş Değeri

*NIndex* tarafından belirtilen konumdaki öğenin bir kopyası. Bu öğe, şablon parametre *türü* tarafından belirtilen türdür.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için bkz [. CObArray:: GetAt](../../mfc/reference/cobarray-class.md#getat)

## <a name="ctypedptrarrayinsertat"></a><a name="insertat"></a> CTypedPtrArray:: InsertAt

Bu üye işlevi `BASE_CLASS` **:: InsertAt** öğesini çağırır.

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

*nDizin*<br/>
[CObArray:: Getüstsınırı](../../mfc/reference/cobarray-class.md#getupperbound)ile döndürülen değerden daha büyük olabilecek bir tamsayı dizini.

*TÜR*<br/>
Temel sınıf dizide depolanan öğelerin türü.

*newElement*<br/>
Bu diziye yerleştirilecek nesne işaretçisi. **Null** değerli bir *newwelement* öğesine izin verilir.

*nCount*<br/>
Bu öğenin Eklenme sayısı (varsayılan 1 ' dir).

*nStartIndex*<br/>
Tarafından döndürülen değerden daha büyük olabilecek bir tamsayı dizini `CObArray::GetUpperBound` .

*BASE_CLASS*<br/>
Türü belirtilmiş işaretçi dizisi sınıfının temel sınıfı; bir dizi sınıfı ( [CObArray](../../mfc/reference/cobarray-class.md) veya [CPtrArray](../../mfc/reference/cptrarray-class.md)) olmalıdır.

*pNewArray*<br/>
Bu diziye eklenecek öğeleri içeren başka bir dizi.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için bkz. [CObArray:: InsertAt](../../mfc/reference/cobarray-class.md#insertat).

## <a name="ctypedptrarrayoperator--"></a><a name="operator_at"></a> CTypedPtrArray:: operator []

Bu satır içi operatörler `BASE_CLASS` **:: operator []** çağrısı.

```
TYPE& operator[ ](int_ptr nindex);
TYPE operator[ ](int_ptr nindex) const;
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Dizide depolanan öğelerin türünü belirten şablon parametresi.

*nDizin*<br/>
0 ' dan büyük veya buna eşit ve `BASE_CLASS` **:: getüstelen** değerden küçük veya buna eşit bir tamsayı dizini.

### <a name="remarks"></a>Açıklamalar

Olmayan diziler için çağrılan ilk operatör **`const`** , atama ifadesinin sağ (r-value) veya Left (l-value) üzerinde kullanılabilir. Diziler için çağrılan ikinci, **`const`** yalnızca sağda kullanılabilir.

Kitaplığın hata ayıklama sürümü, alt simge (atama ifadesinin solunda ya da sağ tarafında) sınırların dışında olup olmadığını onaylar.

## <a name="ctypedptrarraysetat"></a><a name="setat"></a> CTypedPtrArray:: SetAt

Bu üye işlevi `BASE_CLASS` **:: SetAt** çağırır.

```cpp
void SetAt(
    INT_PTR nIndex,
    TYPE ptr);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
0 ' dan büyük veya buna eşit ve [CObArray:: Getüstelen](../../mfc/reference/cobarray-class.md#getupperbound)değere eşit veya ondan küçük bir tamsayı dizini.

*TÜR*<br/>
Temel sınıf dizide depolanan öğelerin türü.

*ptr*<br/>
NIndex öğesinde diziye eklenecek öğe işaretçisi. NULL değere izin verilir.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için bkz. [CObArray:: SetAt](../../mfc/reference/cobarray-class.md#setat).

## <a name="ctypedptrarraysetatgrow"></a><a name="setatgrow"></a> CTypedPtrArray:: SetAtGrow

Bu üye işlevi `BASE_CLASS` **:: SetAtGrow** çağırır.

```cpp
void SetAtGrow(
    INT_PTR nIndex,
    TYPE newElement);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
0 ' dan büyük veya buna eşit bir tamsayı dizini.

*TÜR*<br/>
Temel sınıf dizide depolanan öğelerin türü.

*newElement*<br/>
Bu diziye eklenecek nesne işaretçisi. **Null** değere izin verilir.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için bkz. [CObArray:: SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow).

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek toplama](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CPtrArray sınıfı](../../mfc/reference/cptrarray-class.md)<br/>
[CObArray sınıfı](../../mfc/reference/cobarray-class.md)
