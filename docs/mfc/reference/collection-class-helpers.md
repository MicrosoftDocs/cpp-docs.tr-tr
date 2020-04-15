---
title: Koleksiyon Sınıfı Yardımcıları
ms.date: 11/04/2016
helpviewer_keywords:
- DestructElements function
- ConstructElements function
- SerializeElements function
- collection classes [MFC], helper functions
- helper functions collection class [MFC]
ms.assetid: bc3a2368-9edd-4748-9e6a-13cba79517ca
ms.openlocfilehash: 05fe49a4d8e6de92c584d40f3871f3efb906c7c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374809"
---
# <a name="collection-class-helpers"></a>Koleksiyon Sınıfı Yardımcıları

Toplama sınıfları, `CMap` `CList` `CArray` ve karşılaştırma, kopyalama ve öğeleri serileştirme gibi amaçlar için şablonlanmış genel yardımcı işlevleri kullanın. 'ye `CMap` `CList`ve `CArray`, haritanızda, listenizde veya dizinizde depolanan veri türüne göre uyarlanmış sürümlerle bu işlevleri gerektiği gibi geçersiz kılmanız gerekir. Yardımcı işlevlerin geçersiz kılınması `SerializeElements`hakkında bilgi için, [bkz.](../../mfc/how-to-make-a-type-safe-collection.md) Bunu `ConstructElements` unutmayın `DestructElements` ve amortismana uğradı.

Microsoft Hazırlık Sınıfı Kitaplığı, koleksiyon sınıflarınızı özelleştirmenize yardımcı olmak için afxtempl.h'de aşağıdaki genel işlevleri sağlar:

### <a name="collection-class-helpers"></a>Koleksiyon Sınıfı Yardımcıları

|||
|-|-|
|[Öğeleri Karşılaştır](#compareelements)|Öğelerin aynı olup olmadığını gösterir.|
|[CopyElements](#copyelements)|Öğeleri bir diziden diğerine kopyalar.|
|[Döküm Elemanları](#dumpelements)|Akış odaklı tanı çıktısı sağlar.|
|[HashKey](#hashkey)|Karma anahtarı hesaplar.|
|[SerializeElements](#serializeelements)|Bir arşive veya arşivden öğeleri depolar veya alır.|

## <a name="compareelements"></a><a name="compareelements"></a>Öğeleri Karşılaştır

Doğrudan [CList::Find](clist-class.md#not_found.md#clist__find ve dolaylı olarak [cmap__lookup](cmap-class.md#lookup) ve [cmap__operator &#91;&#93;](cmap-class.md#operator_at)tarafından çağrılır.

```
template<class TYPE, class ARG_TYPE>
BOOL AFXAPI
CompareElements(
    const TYPE* pElement1,
    const ARG_TYPE* pElement2);
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Karşılaştırılacak ilk öğenin türü.

*pElement1*<br/>
Karşılaştırılacak ilk öğeyi işaretle.

*ARG_TYPE*<br/>
Karşılaştırılacak ikinci öğenin türü.

*pElement2*<br/>
Karşılaştırılacak ikinci öğeyi işaretçi.

### <a name="return-value"></a>Dönüş Değeri

*pElement1* tarafından işaret edilen nesne *pElement2*tarafından işaret edilen nesneye eşitse sıfır yok; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CMap` Aramalar şablon `CMap` parametreleri *KEY* ve *ARG_KEY*kullanın.

Varsayılan uygulama * \*pElement1* ve * \*pElement2*karşılaştırma sonucu döndürür. Bu işlevi, öğeleri uygulamanız için uygun şekilde karşılaştıracak şekilde geçersiz kılın.

C++ `==`dili basit türleri **(char**, **int**, **float**, vb.) için karşılaştırma işleci ( ) tanımlar, ancak sınıflar ve yapılar için bir karşılaştırma işleci tanımlamaz. Bunu kullanan koleksiyon `CompareElements` sınıflarından birini kullanmak veya anlık olarak kullanmak istiyorsanız, karşılaştırma işlecitanımlamanız `CompareElements` veya uygun değerleri döndüren bir sürümle aşırı yüklemeniz gerekir.

### <a name="requirements"></a>Gereksinimler

   **Başlık:** afxtempl.h

## <a name="copyelements"></a><a name="copyelements"></a>CopyElements

Bu işlev doğrudan [CArray tarafından çağrılır::Append](carray-class.md#append) ve [CArray::Copy](carray-class.md#copy).

```
template<class TYPE>
void AFXAPI CopyElements(
    TYPE* pDest,
    const TYPE* pSrc,
    INT_PTR nCount);
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Kopyalanacak öğelerin türünü belirten şablon parametresi.

*pDest*<br/>
Öğelerin kopyalanacağı hedefe işaretçi.

*pSrc*<br/>
Kopyalanacak öğelerin kaynağına işaretçi.

*nSayısı*<br/>
Kopyalanacak öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, kopyalama işlemini **=** gerçekleştirmek için basit atama işleci ( ) kullanır. Kopyalanan türde aşırı yüklü bir işleci=yoksa, varsayılan uygulama bityönünde bir kopya gerçekleştirir.

Bu ve diğer yardımcı işlevlerin uygulanması hakkında bilgi için, makale [Koleksiyonları: Nasıl Tür Güvenli Toplama olun.](../how-to-make-a-type-safe-collection.md)

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxtempl.h

## <a name="dumpelements"></a><a name="dumpelements"></a>Döküm Elemanları

Geçersiz kılındığında koleksiyonunuzun öğeleri için metin biçiminde akış odaklı tanı çıktısı sağlar.

```
template<class TYPE>
void  AFXAPI DumpElements(
    CDumpContext& dc,
    const TYPE* pElements,
    INT_PTR nCount);
```

### <a name="parameters"></a>Parametreler

*Dc*<br/>
Öğeleri dökümü için bağlamı dökümü.

*TÜR*<br/>
Öğelerin türünü belirten şablon parametresi.

*pElements*<br/>
Atılacak öğeleriçin işaretçi.

*nSayısı*<br/>
Boşaltılacak öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Dökümün derinliği 0'dan `CArray::Dump`büyükse, ve `CList::Dump` `CMap::Dump` işlevler bunu çağırır.

Varsayılan uygulama hiçbir şey yapmaz. Koleksiyonunuzdaki öğeler `CObject`türetilmişse, geçersiz kılmanız genellikle koleksiyonun öğeleri arasında `Dump` yinelenir ve her öğeyi sırayla çağıracaktır.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxtempl.h

## <a name="hashkey"></a><a name="hashkey"></a>HashKey

Verilen anahtar için karma değeri hesaplar.

```
template<class ARG_KEY>
AFX_INLINE UINT AFXAPI HashKey(ARG_KEY  key);
```

### <a name="parameters"></a>Parametreler

*ARG_KEY*<br/>
Harita anahtarlarına erişmek için kullanılan veri türünü belirten şablon parametresi.

*anahtar*<br/>
Karma değeri hesaplanacak anahtar.

### <a name="return-value"></a>Dönüş Değeri

Anahtarın karma değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlev doğrudan [CMap tarafından çağrılır::RemoveKey](cmap-class.md#removekey) ve dolaylı [olarak CMap::Lookup](cmap-class.md#lookup) ve [CMap::Operator &#91;&#93;](cmap-class.md#operator_at).

Varsayılan uygulama, *anahtar* sağa dört konuma kaydırarak karma bir değer oluşturur. Bu işlevi, uygulamanız için uygun karma değerleri döndürecek şekilde geçersiz kılın.

### <a name="example"></a>Örnek

```cpp
template <> UINT AFXAPI HashKey(unsigned __int64 key)
{
   // Generate the hash value by XORing the lower 32 bits of the number
   // with the upper 32 bits
   return(UINT(key) ^ UINT(key >> 32));
}
```

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxtempl.h

## <a name="serializeelements"></a><a name="serializeelements"></a>SerializeElements

[CArray](carray-class.md), [CList](clist-class.md)ve [CMap](cmap-class.md) öğeleri serihale etmek için bu işlevi arayın.

```
template<class TYPE>
void AFXAPI SerializeElements(CArchive& ar, TYPE* pElements, INT_PTR nCount);
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Öğelerin türünü belirten şablon parametresi.

*Ar*<br/>
Arşivlemek için veya gelen bir arşiv nesnesi.

*pElements*<br/>
Arşivlenmiş öğeleriçin işaretçi.

*nSayısı*<br/>
Arşivlendirilen öğe sayısı

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama biraz akıllıca okuma veya yazma yapar.

Bu ve diğer yardımcı işlevlerin uygulanması hakkında bilgi için, makale [Koleksiyonları: Nasıl Tür Güvenli Toplama olun.](../how-to-make-a-type-safe-collection.md)

### <a name="example"></a>Örnek

Koleksiyonlar makaledeki örneğe [bakın: Tür Güvenli Toplama Nasıl Yapılır.](../how-to-make-a-type-safe-collection.md)

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxtempl.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](mfc-macros-and-globals.md)<br/>
[CMap Sınıfı](cmap-class.md)<br/>
[CList Sınıfı](clist-class.md)<br/>
[CArray Sınıfı](carray-class.md)
