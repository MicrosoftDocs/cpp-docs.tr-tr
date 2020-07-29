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
ms.openlocfilehash: 02bc5c5a7c1766c97d9a834c8b6b4dfb2a26ae82
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231799"
---
# <a name="collection-class-helpers"></a>Koleksiyon Sınıfı Yardımcıları

Koleksiyon sınıfları, `CMap` `CList` ve `CArray` öğeleri karşılaştırma, kopyalama ve serileştirme gibi amaçlar için şablonlu genel yardımcı işlevleri kullanır. , Ve ' a dayanan sınıfların bir parçası olarak `CMap` , `CList` `CArray` Bu işlevleri haritada, listenizde veya dizide depolanan verilerin türüne uyarlanmış sürümlerle gerektiği şekilde geçersiz kılmanız gerekir. Gibi yardımcı işlevleri geçersiz kılma hakkında daha fazla bilgi için `SerializeElements` bkz. [Koleksiyonlar: tür kullanımı uyumlu koleksiyon yapma](../../mfc/how-to-make-a-type-safe-collection.md). Bu `ConstructElements` ve `DestructElements` kullanım dışı bırakılmış olduğunu unutmayın.

Microsoft Foundation Class Kitaplığı, topluluk sınıflarınızı özelleştirmenize yardımcı olması için afxtempl. h ' de aşağıdaki genel işlevleri sağlar:

### <a name="collection-class-helpers"></a>Koleksiyon Sınıfı Yardımcıları

|||
|-|-|
|[CompareElements](#compareelements)|Öğelerin aynı olup olmadığını gösterir.|
|[CopyElements](#copyelements)|Öğeleri bir diziden diğerine kopyalar.|
|[DumpElements](#dumpelements)|Akışa dayalı tanılama çıkışı sağlar.|
|[HashKey](#hashkey)|Bir karma anahtarı hesaplar.|
|[SerializeElements](#serializeelements)|Bir arşive veya bir arşivden öğeleri depolar veya alır.|

## <a name="compareelements"></a><a name="compareelements"></a>CompareElements

Doğrudan [CList:: Find] (CList-Class. MD # not_found. MD # clist__find ve dolaylı olarak [cmap__lookup](cmap-class.md#lookup) ve [cmap__operator &#91;&#93;](cmap-class.md#operator_at)tarafından çağırılır.

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
Karşılaştırılacak ilk öğe işaretçisi.

*ARG_TYPE*<br/>
Karşılaştırılacak ikinci öğe türü.

*pElement2*<br/>
Karşılaştırılacak ikinci öğe işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

*PElement1* tarafından işaret edilen nesne, *pElement2*tarafından işaret edilen nesneye eşitse sıfır dışı olur; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CMap`Çağrılar, `CMap` şablon parametreleri *anahtarını* ve *ARG_KEY*kullanır.

Varsayılan uygulama, * \* pElement1* ve * \* pElement2*' nin karşılaştırmasının sonucunu döndürür. Öğeleri uygulamanız için uygun bir şekilde karşılaştıran şekilde bu işlevi geçersiz kılın.

C++ dili `==` basit türler (,, vb.) için karşılaştırma işlecini () tanımlar, **`char`** **`int`** **`float`** ancak sınıflar ve yapılar için bir karşılaştırma işleci tanımlamaz. `CompareElements`Bunu kullanan koleksiyon sınıflarından birini oluşturmak için veya kullanmak istiyorsanız, karşılaştırma işlecini veya aşırı yüklemeyi `CompareElements` uygun değerleri döndüren bir sürümle tanımlamanız gerekir.

### <a name="requirements"></a>Gereksinimler

   **Üstbilgi:** afxtempl. h

## <a name="copyelements"></a><a name="copyelements"></a>CopyElements

Bu işlev doğrudan [CArray:: Append](carray-class.md#append) ve [CArray:: Copy](carray-class.md#copy)tarafından çağrılır.

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
Öğelerin kopyalanacağı hedef işaretçisi.

*pSrc*<br/>
Kopyalanacak öğelerin kaynağı işaretçisi.

*nCount*<br/>
Kopyalanacak öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, **=** kopyalama işlemini gerçekleştirmek için basit atama işlecini () kullanır. Kopyalanmakta olan türün aşırı yüklenmiş bir işleci yoksa, varsayılan uygulama bit düzeyinde bir kopya gerçekleştirir.

Bu ve diğer yardımcı işlevleri uygulama hakkında daha fazla bilgi için bkz. [Koleksiyonlar: tür kullanımı uyumlu koleksiyon yapma](../how-to-make-a-type-safe-collection.md).

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxtempl. h

## <a name="dumpelements"></a><a name="dumpelements"></a>DumpElements

Geçersiz kılınırsa, koleksiyonunuzdaki öğeler için akışa yönelik tanılama çıkışı metin biçiminde sağlar.

```
template<class TYPE>
void  AFXAPI DumpElements(
    CDumpContext& dc,
    const TYPE* pElements,
    INT_PTR nCount);
```

### <a name="parameters"></a>Parametreler

*'ye*<br/>
Döküm öğeleri için döküm bağlamı.

*TÜR*<br/>
Öğelerin türünü belirten şablon parametresi.

*pElements*<br/>
Dökülebilir öğelere yönelik işaretçi.

*nCount*<br/>
Döküme yapılacak öğe sayısı.

### <a name="remarks"></a>Açıklamalar

`CArray::Dump`, `CList::Dump` , Ve `CMap::Dump` işlevleri, döküm derinliği 0 ' dan büyükse bunu çağırır.

Varsayılan uygulama hiçbir şey yapmaz. Koleksiyonunuzun öğeleri öğesinden türetildiyse `CObject` , geçersiz kılma, genellikle koleksiyonun öğeleri boyunca yinelenir ve `Dump` her öğe için sırasıyla çağrı yapılır.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxtempl. h

## <a name="hashkey"></a><a name="hashkey"></a>HashKey

Verilen anahtar için bir karma değeri hesaplar.

```
template<class ARG_KEY>
AFX_INLINE UINT AFXAPI HashKey(ARG_KEY  key);
```

### <a name="parameters"></a>Parametreler

*ARG_KEY*<br/>
Harita anahtarlarına erişmek için kullanılan veri türünü belirten şablon parametresi.

*anahtar*<br/>
Karma değeri hesaplanacak olan anahtar.

### <a name="return-value"></a>Dönüş Değeri

Anahtarın karma değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlev doğrudan [CMap](cmap-class.md#removekey) :: RemoveKey ve dolaylı olarak [CMap:: Lookup](cmap-class.md#lookup) ve [cmap:: operator &#91;&#93;](cmap-class.md#operator_at)tarafından çağrılır.

Varsayılan uygulama, *anahtarı* sağ dört konum ile değiştirerek bir karma değer oluşturur. Uygulamanız için uygun olan karma değerleri döndürmesi için bu işlevi geçersiz kılın.

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

  **Başlık** afxtempl. h

## <a name="serializeelements"></a><a name="serializeelements"></a>SerializeElements

[CArray](carray-class.md), [CList](clist-class.md)ve [CMap](cmap-class.md) öğeleri seri hale getirmek için bu işlevi çağırır.

```
template<class TYPE>
void AFXAPI SerializeElements(CArchive& ar, TYPE* pElements, INT_PTR nCount);
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Öğelerin türünü belirten şablon parametresi.

*Ar*<br/>
Arşivlemek için bir arşiv nesnesi.

*pElements*<br/>
Arşivlenen öğelere yönelik işaretçi.

*nCount*<br/>
Arşivlenen öğe sayısı

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama bit düzeyinde okuma veya yazma yapmaz.

Bu ve diğer yardımcı işlevleri uygulama hakkında daha fazla bilgi için bkz. [Koleksiyonlar: tür kullanımı uyumlu koleksiyon yapma](../how-to-make-a-type-safe-collection.md).

### <a name="example"></a>Örnek

Makale [koleksiyonları: tür kullanımı uyumlu koleksiyon yapma](../how-to-make-a-type-safe-collection.md)içindeki örneğe bakın.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxtempl. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](mfc-macros-and-globals.md)<br/>
[CMap sınıfı](cmap-class.md)<br/>
[CList sınıfı](clist-class.md)<br/>
[CArray sınıfı](carray-class.md)
