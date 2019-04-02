---
title: CTypedPtrArray Class
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
ms.openlocfilehash: 080e47746b83b6ff12db9f6df0fc27bcd202bb51
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58768698"
---
# <a name="ctypedptrarray-class"></a>CTypedPtrArray Class

Sınıfındaki nesneler için tür açısından güvenli bir "sarmalayıcı" sağlar `CPtrArray` veya `CObArray`.

## <a name="syntax"></a>Sözdizimi

```
template<class BASE_CLASS, class TYPE>
class CTypedPtrArray : public BASE_CLASS
```

#### <a name="parameters"></a>Parametreler

*BASE_CLASS*<br/>
İşaretçi türü belirlenmiş dizi sınıfın temel sınıfına; array sınıfı olmalıdır ( `CObArray` veya `CPtrArray`).

*TÜRÜ*<br/>
Temel sınıf dizisinde depolanan öğelerin türü.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CTypedPtrArray::Add](#add)|Bir dizinin sonuna yeni bir öğe ekler. Gerekirse, dizi büyüyor|
|[CTypedPtrArray::Append](#append)|Bir dizinin içeriğini başka sonuna ekler. Gerekirse, dizi büyüyor|
|[CTypedPtrArray::Copy](#copy)|Diziyi başka diziye kopyalar; dizi gerekirse büyür.|
|[CTypedPtrArray::ElementAt](#elementat)|Dizi içinde öğe işaretçisi için geçici bir başvuru döndürür.|
|[CTypedPtrArray::GetAt](#getat)|Belirtilen dizindeki değeri döndürür.|
|[CTypedPtrArray::InsertAt](#insertat)|Belirtilen dizindeki öğenin (veya başka bir dizideki tüm öğeler) ekler.|
|[CTypedPtrArray::SetAt](#setat)|Belirtilen dizin için değeri ayarlar; dizi büyümesine izin verilmiyor.|
|[CTypedPtrArray::SetAtGrow](#setatgrow)|Belirtilen dizin için değeri ayarlar; dizi gerekirse büyür.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CTypedPtrArray::operator \[ \]](#operator_at)|Belirtilen dizindeki öğeyi alır veya ayarlar.|

## <a name="remarks"></a>Açıklamalar

Kullanırken `CTypedPtrArray` yerine `CPtrArray` veya `CObArray`, C++ tür denetimi olanağı eşleşmeyen işaretçi türleri tarafından neden olduğu hata ortadan yardımcı olur.

Ayrıca, `CTypedPtrArray` sarmalayıcı kullandıysanız, gerekli olacak atama çoğunu gerçekleştirir `CObArray` veya `CPtrArray`.

Çünkü tüm `CTypedPtrArray` satır içi işlevlerdir, bu şablonun kullanımını boyut veya hız kodunuzun önemli ölçüde etkilemez.

Kullanma hakkında daha fazla bilgi için `CTypedPtrArray`, makalelere göz atın [koleksiyonları](../../mfc/collections.md) ve [şablona dayalı sınıflar](../../mfc/template-based-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`BASE_CLASS`

`CTypedPtrArray`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxtempl.h

##  <a name="add"></a>  CTypedPtrArray::Add

Bu üye işlevini çağırır `BASE_CLASS` **:: Ekle**.

```
INT_PTR Add(TYPE newElement);
```

### <a name="parameters"></a>Parametreler

*TÜRÜ*<br/>
Diziye eklenecek öğe türünü belirten bir şablon parametre.

*newElement*<br/>
Bu diziye eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

Eklenen öğenin dizini.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için bkz. [CObArray::Add](../../mfc/reference/cobarray-class.md#add).

##  <a name="append"></a>  CTypedPtrArray::Append

Bu üye işlevini çağırır `BASE_CLASS`:: Ekle **.

```
INT_PTR Append(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```

### <a name="parameters"></a>Parametreler

*BASE_CLASS*<br/>
İşaretçi türü belirlenmiş dizi sınıfın temel sınıfına; array sınıfı olmalıdır ( [CObArray](../../mfc/reference/cobarray-class.md) veya [CPtrArray](../../mfc/reference/cptrarray-class.md)).

*TÜRÜ*<br/>
Temel sınıf dizisinde depolanan öğelerin türü.

*src*<br/>
Kaynak bir diziye eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

Eklenen ilk öğenin dizini.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için bkz. [CObArray::Append](../../mfc/reference/cobarray-class.md#append).

##  <a name="copy"></a>  CTypedPtrArray::Copy

Bu üye işlevini çağırır `BASE_CLASS` **:: kopyalama**.

```
void Copy(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```

### <a name="parameters"></a>Parametreler

*BASE_CLASS*<br/>
İşaretçi türü belirlenmiş dizi sınıfın temel sınıfına; array sınıfı olmalıdır ( [CObArray](../../mfc/reference/cobarray-class.md) veya [CPtrArray](../../mfc/reference/cptrarray-class.md)).

*TÜRÜ*<br/>
Temel sınıf dizisinde depolanan öğelerin türü.

*src*<br/>
Bir diziye kopyalanacak öğe kaynağı.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için bkz. [CObArray::Copy](../../mfc/reference/cobarray-class.md#copy).

##  <a name="elementat"></a>  CTypedPtrArray::ElementAt

Bu satır içi işlev çağrıları `BASE_CLASS` **:: ElementAt**.

```
TYPE& ElementAt(INT_PTR nIndex);
```

### <a name="parameters"></a>Parametreler

*TÜRÜ*<br/>
Şablon parametresi bu dizinin içinde depolanan öğelerin türünü belirtme.

*nIndex*<br/>
Büyük veya 0'a eşit bir tamsayı dizini ve tarafından döndürülen değer küçüktür veya eşittir `BASE_CLASS` **:: GetUpperBound**.

### <a name="return-value"></a>Dönüş Değeri

Öğesi tarafından belirtilen konumda bir geçici başvuru *nIndex*. Bu öğe şablon parametresi tarafından belirtilen tür olduğu *türü*.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için bkz. [CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat).

##  <a name="getat"></a>  CTypedPtrArray::GetAt

Bu satır içi işlev çağrıları `BASE_CLASS` **:: GetAt**.

```
TYPE GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Parametreler

*TÜRÜ*<br/>
Depolanan dizideki öğelerin türünü belirten bir şablon parametre.

*nIndex*<br/>
Büyük veya 0'a eşit bir tamsayı dizini ve tarafından döndürülen değer küçüktür veya eşittir `BASE_CLASS` **:: GetUpperBound**.

### <a name="return-value"></a>Dönüş Değeri

Öğesi tarafından belirtilen konumda bir kopyasını *nIndex*. Bu öğe şablon parametresi tarafından belirtilen tür olduğu *türü*.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için bkz. [CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)

##  <a name="insertat"></a>  CTypedPtrArray::InsertAt

Bu üye işlevini çağırır `BASE_CLASS` **:: InsertAt**.

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

*nIndex*<br/>
Tarafından döndürülen değeri,'den büyük bir tamsayı dizini [CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound).

*TÜRÜ*<br/>
Temel sınıf dizisinde depolanan öğelerin türü.

*newElement*<br/>
Bu dizinin içinde yerleştirilecek nesne işaretçisi. A *newElement* değerinin **NULL** izin verilir.

*nCount*<br/>
Bu öğe olmalıdır sayısı (varsayılan 1) eklenir.

*nStartIndex*<br/>
Tarafından döndürülen değeri,'den büyük bir tamsayı dizini `CObArray::GetUpperBound`.

*BASE_CLASS*<br/>
İşaretçi türü belirlenmiş dizi sınıfın temel sınıfına; array sınıfı olmalıdır ( [CObArray](../../mfc/reference/cobarray-class.md) veya [CPtrArray](../../mfc/reference/cptrarray-class.md)).

*pNewArray*<br/>
Bu diziye eklenecek öğeleri içeren başka bir dizi.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için bkz. [CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat).

##  <a name="operator_at"></a>  CTypedPtrArray::operator]

Bu satır içi işleçler çağrı `BASE_CLASS` **:: operator []**.

```
TYPE& operator[ ](int_ptr nindex);
TYPE operator[ ](int_ptr nindex) const;
```

### <a name="parameters"></a>Parametreler

*TÜRÜ*<br/>
Depolanan dizideki öğelerin türünü belirten bir şablon parametre.

*nIndex*<br/>
Büyük veya 0'a eşit bir tamsayı dizini ve tarafından döndürülen değer küçüktür veya eşittir `BASE_CLASS` **:: GetUpperBound**.

### <a name="remarks"></a>Açıklamalar

İlk işleç değil diziler için çağrılır **const**, sağ (r) veya Atama ifadesinin solunda (lvalue) üzerinde kullanılabilir. İkincisi, çağrılan için **const** diziler, sağ tarafta yalnızca kullanılabilir.

Kitaplığı hata ayıklama sürümünü (veya sol veya sağ tarafında bir atama ifadesi) alt simge sınırların dışında olup olmadığını onaylar.

##  <a name="setat"></a>  CTypedPtrArray::SetAt

Bu üye işlevini çağırır `BASE_CLASS` **:: SetAt**.

```
void SetAt(
    INT_PTR nIndex,
    TYPE ptr);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Büyük veya 0'a eşit bir tamsayı dizini ve tarafından döndürülen değer küçüktür veya eşittir [CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound).

*TÜRÜ*<br/>
Temel sınıf dizisinde depolanan öğelerin türü.

*ptr*<br/>
Dizide nIndex eklenecek öğe için bir işaretçi. NULL değerine izin verilir.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için bkz. [CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat).

##  <a name="setatgrow"></a>  CTypedPtrArray::SetAtGrow

Bu üye işlevini çağırır `BASE_CLASS` **:: SetAtGrow**.

```
void SetAtGrow(
    INT_PTR nIndex,
    TYPE newElement);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Büyük veya 0'a eşit bir tamsayı dizini.

*TÜRÜ*<br/>
Temel sınıf dizisinde depolanan öğelerin türü.

*newElement*<br/>
Bu diziye eklenecek nesne işaretçisi. A **NULL** değere izin verilir.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için bkz. [CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow).

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek Topla](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CPtrArray Sınıfı](../../mfc/reference/cptrarray-class.md)<br/>
[CObArray Sınıfı](../../mfc/reference/cobarray-class.md)
