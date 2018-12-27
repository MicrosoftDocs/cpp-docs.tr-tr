---
title: CMap sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMap
- AFXTEMPL/CMap
- AFXTEMPL/CMap::CPair
- AFXTEMPL/CMap::CMap
- AFXTEMPL/CMap::GetCount
- AFXTEMPL/CMap::GetHashTableSize
- AFXTEMPL/CMap::GetNextAssoc
- AFXTEMPL/CMap::GetSize
- AFXTEMPL/CMap::GetStartPosition
- AFXTEMPL/CMap::InitHashTable
- AFXTEMPL/CMap::IsEmpty
- AFXTEMPL/CMap::Lookup
- AFXTEMPL/CMap::PGetFirstAssoc
- AFXTEMPL/CMap::PGetNextAssoc
- AFXTEMPL/CMap::PLookup
- AFXTEMPL/CMap::RemoveAll
- AFXTEMPL/CMap::RemoveKey
- AFXTEMPL/CMap::SetAt
helpviewer_keywords:
- CMap [MFC], CPair
- CMap [MFC], CMap
- CMap [MFC], GetCount
- CMap [MFC], GetHashTableSize
- CMap [MFC], GetNextAssoc
- CMap [MFC], GetSize
- CMap [MFC], GetStartPosition
- CMap [MFC], InitHashTable
- CMap [MFC], IsEmpty
- CMap [MFC], Lookup
- CMap [MFC], PGetFirstAssoc
- CMap [MFC], PGetNextAssoc
- CMap [MFC], PLookup
- CMap [MFC], RemoveAll
- CMap [MFC], RemoveKey
- CMap [MFC], SetAt
ms.assetid: 640a45ab-0993-4def-97ec-42cc78eb10b9
ms.openlocfilehash: 88ca218d4cb4e70dcc46ba04bbdfb7a9d12eb808
ms.sourcegitcommit: 53f75afaf3c0b3ed481c5503357ed2b7b87aac6d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2018
ms.locfileid: "53657584"
---
# <a name="cmap-class"></a>CMap sınıfı

Benzersiz anahtarlar ve değerleri eşleyen sözlük koleksiyon sınıfı.

## <a name="syntax"></a>Sözdizimi

```
template<class KEY, class ARG_KEY, class VALUE, class ARG_VALUE>class CMap : public CObject
```

#### <a name="parameters"></a>Parametreler

*KEY*<br/>
Harita anahtarı olarak kullanılan nesne sınıfı.

*ARG_KEY*<br/>
Veri türü için kullanılan *anahtarı* bağımsız değişkenler; genellikle bir başvuru *anahtar*.

*DEĞER*<br/>
Eşlem içinde depolan bir nesne sınıfı.

*ARG_VALUE*<br/>
Veri türü için kullanılan *değer* bağımsız değişkenler; genellikle bir başvuru *değer*.

## <a name="members"></a>Üyeler

### <a name="public-structures"></a>Genel yapılar

|Ad|Açıklama|
|----------|-----------------|
|[CMap::CPair](#cpair)|Bir anahtar değeri ve ilişkili nesne değeri içeren bir iç içe geçmiş yapısı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMap::CMap](#cmap)|Anahtarlar ve değerleri eşleyen bir koleksiyon oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMap::GetCount](#getcount)|Bu haritada öğelerin sayısını döndürür.|
|[CMap::GetHashTableSize](#gethashtablesize)|Karma tablodaki öğelerin sayısını döndürür.|
|[CMap::GetNextAssoc](#getnextassoc)|Yineleme için sonraki öğeyi alır.|
|[CMap::GetSize](#getsize)|Bu haritada öğelerin sayısını döndürür.|
|[CMap::GetStartPosition](#getstartposition)|İlk öğenin konumunu döndürür.|
|[CMap::InitHashTable](#inithashtable)|Karma tablo başlatır ve boyutunu belirtir.|
|[CMap::IsEmpty](#isempty)|(Öğe yok) boş-map koşulu sınar.|
|[CMap::Lookup](#lookup)|Belirli bir anahtar ile eşlenen değeri arar.|
|[CMap::PGetFirstAssoc](#pgetfirstassoc)|İlk öğeye bir işaretçi döndürür.|
|[CMap::PGetNextAssoc](#pgetnextassoc)|Bir işaretçi, yineleme için sonraki öğeyi alır.|
|[CMap::PLookup](#plookup)|Değeri belirtilen değerle eşleşen bir anahtara bir işaretçi döndürür.|
|[CMap::RemoveAll](#removeall)|Tüm öğeleri bu eşlemden kaldırır.|
|[CMap::RemoveKey](#removekey)|Bir anahtar tarafından belirtilen bir öğeyi kaldırır.|
|[CMap::SetAt](#setat)|Haritayı bir öğe ekler; eşleşen bir anahtar bulunursa, var olan öğenin yerini alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CMap::operator \[ \]](#operator_at)|Haritayı bir öğe ekler; işleci alternatifi için `SetAt`.|

## <a name="remarks"></a>Açıklamalar

Haritayı bir anahtar-değer çifti (öğesi) ekledikten sonra verimli bir şekilde alın veya erişim anahtarı kullanılarak çifti silin. Eşlem içindeki tüm öğeleri üzerinde yineleyebilirsiniz.

KONUM türünde bir değişken, girişler için alternatif erişim için kullanılır. Bir konum "unutmayın bir giriş için" ve eşlemesi üzerinden yineleme yapmak için kullanabilirsiniz. Bu yineleme anahtar değere göre sıralı olduğunu düşünebilirsiniz; Bu değil. Alınan öğe dizisi belirsiz.

Bu sınıf, genel yardımcı işlevleri çağrının belirli üye işlevleri, çoğu kullanım için özelleştirilmelidir `CMap` sınıfı. Bkz: [koleksiyon sınıfı Yardımcıları](../../mfc/reference/collection-class-helpers.md) makroları ve genel öğeleri bölümünde **MFC başvurusu**.

`CMap` geçersiz kılmalar [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) seri hale getirme ve alt öğeleri dökme desteklemek için. Bir arşiv kullanarak bir harita depolanıyorsa `Serialize`, her harita öğesini sırayla serileştirilir. Varsayılan uygulaması `SerializeElements` yardımcı işlevi, bit düzeyinde bir yazma yapar. Türetilen seri hale getirme işaretçi koleksiyonu öğelerinin hakkında bilgi için `CObject` veya diğer kullanıcı tanımlı türleri [nasıl yapılır: Tür kullanımı uyumlu koleksiyon yapma](../../mfc/how-to-make-a-type-safe-collection.md).

Bir tanılama dökümü (anahtarlar ve değerler) map tek tek öğelerin gerekiyorsa, 1 veya daha büyük derinliği döküm bağlam ayarlamanız gerekir.

Olduğunda bir `CMap` nesnesi silindiğinde veya anahtarları ve değerleri öğelerine kaldırıldığında kaldırılır.

Map sınıfı türetme için liste türetme benzerdir. Makaleye göz atın [koleksiyonları](../../mfc/collections.md) özel amaçlı listesi sınıfının türetme bir gösterim.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CMap`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxtempl.h

##  <a name="cmap"></a>  CMap::CMap

Boş bir harita oluşturur.

```
CMap(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Harita genişletmek için bellek ayırma ayrıntı düzeyi belirtir.

### <a name="remarks"></a>Açıklamalar

Harita büyüdükçe, birimleri cinsinden ayrılan bellek *nBlockSize* girdileri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#56](../../mfc/codesnippet/cpp/cmap-class_1.cpp)]

##  <a name="cpair"></a>  CMap::CPair

Bir anahtar değeri ve ilişkili nesne değeri içerir.

### <a name="remarks"></a>Açıklamalar

Bu bir sınıf içinde iç içe geçmiş yapısıdır [CMap](../../mfc/reference/cmap-class.md).

Yapısı iki alandan oluşur:

- `key` Anahtar türü gerçek değeri.

- `value` İlişkili nesne değeri.

Dönüş değerleri depolamak için kullanılan [CMap::PLookup](#plookup), [CMap::PGetFirstAssoc](#pgetfirstassoc), ve [CMap::PGetNextAssoc](#pgetnextassoc).

### <a name="example"></a>Örnek

Kullanım örneği için örneğin bakın [CMap::PLookup](#plookup).

##  <a name="getcount"></a>  CMap::GetCount

Eşlem içindeki öğelerin sayısını alır.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğe sayısı.

### <a name="example"></a>Örnek

Örneğin bakın [CMap::Lookup](#lookup).

##  <a name="gethashtablesize"></a>  CMap::GetHashTableSize

Harita karma tablosundaki öğelerin sayısını belirler.

```
UINT GetHashTableSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Karma tablosundaki öğelerin sayısı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#57](../../mfc/codesnippet/cpp/cmap-class_2.cpp)]

##  <a name="getnextassoc"></a>  CMap::GetNextAssoc

Harita öğe alır `rNextPosition`, ardından güncelleştirmeleri `rNextPosition` haritadaki sonraki öğeye başvurmak için.

```
void GetNextAssoc(
    POSITION& rNextPosition,
    KEY& rKey,
    VALUE& rValue) const;
```

### <a name="parameters"></a>Parametreler

*rNextPosition*<br/>
Bir önceki tarafından döndürülen bir konum değeri bir başvuru belirtir `GetNextAssoc` veya `GetStartPosition` çağırın.

*KEY*<br/>
Haritanın anahtar türünü belirten bir şablon parametre.

*rKey*<br/>
Alınan öğenin döndürülen anahtarını belirtir.

*DEĞER*<br/>
Haritanın değerin türünü belirten bir şablon parametre.

*rValue*<br/>
Alınan öğenin döndürülen değeri belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işlev bir eşlem içindeki tüm öğeleri arasında yineleme için kullanışlıdır. Konumu sıranın mutlaka anahtar değeri serisi ile aynı olmadığını unutmayın.

Alınan öğe eşlem içindeki son öğesinin yeni değeri ise *rNextPosition* NULL olarak ayarlandı.

### <a name="example"></a>Örnek

Örneğin bakın [CMap::SetAt](#setat).

##  <a name="getsize"></a>  CMap::GetSize

Harita öğelerin sayısını döndürür.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eşlem içindeki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Eşlem içindeki öğelerin sayısını almak için bu yöntemi çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]

##  <a name="getstartposition"></a>  CMap::GetStartPosition

Harita yineleme, geçirilebilir bir konum değeri döndürerek başlar bir `GetNextAssoc` çağırın.

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Harita yineleme için bir başlangıç konumunu belirten bir konum değeri; ya da bir eşlem boşsa, NULL.

### <a name="remarks"></a>Açıklamalar

Yineleme sırası tahmin edilebilir değil; Bu nedenle, "eşlem içindeki ilk öğeyi" özel bir önemi yoktur.

### <a name="example"></a>Örnek

Örneğin bakın [CMap::SetAt](#setat).

##  <a name="inithashtable"></a>  CMap::InitHashTable

Karma tablo başlatır.

```
void InitHashTable(UINT hashSize, BOOL  bAllocNow = TRUE);
```

### <a name="parameters"></a>Parametreler

*hashSize*<br/>
Girdi karma tablosunda sayısı.

*bAllocNow*<br/>
TRUE ise başlatma sırasında karma tablo ayırır; Aksi takdirde tablo gerektiğinde ayrılır.

### <a name="remarks"></a>Açıklamalar

En iyi performans için bir karma tablo boyutu olmalıdır. Çakışmaları en aza indirmek için boyutu yaklaşık yüzde 20 oranında daha büyük beklenen veri kümesi daha büyük olmalıdır.

### <a name="example"></a>Örnek

Örneğin bakın [CMap::Lookup](#lookup).

##  <a name="isempty"></a>  CMap::IsEmpty

Harita boş olup olmadığını belirler.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu harita hiçbir öğe içeren olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

Örneğin bakın [CMap::RemoveAll](#removeall).

##  <a name="lookup"></a>  CMap::Lookup

Belirli bir anahtar ile eşlenen değeri arar.

```
BOOL Lookup(ARG_KEY key, VALUE& rValue) const;
```

### <a name="parameters"></a>Parametreler

*ARG_KEY*<br/>
Şablon parametresinin türünü belirleyen *anahtar* değeri.

*anahtar*<br/>
Bakılacak öğeyi tanımlayan anahtar belirtir.

*DEĞER*<br/>
Bakılacak değerin türünü belirtir.

*rValue*<br/>
Aranan yukarı değerini alır.

### <a name="return-value"></a>Dönüş Değeri

Öğesi bulundu; olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

`Lookup` eşleme öğesi tam olarak belirtilen anahtarla eşleşen bir anahtar ile hızla bulmak için bir karma algoritma kullanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]

##  <a name="operator_at"></a>  CMap::operator]

Uygun bir alternatif için `SetAt` üye işlevi.

```
VALUE& operator[](arg_key key);
```

### <a name="parameters"></a>Parametreler

*DEĞER*<br/>
Harita değerin türünü belirten bir şablon parametre.

*ARG_KEY*<br/>
Anahtar değeri türünü belirten bir şablon parametre.

*anahtar*<br/>
Haritadaki değerini almak için kullanılan anahtar.

### <a name="remarks"></a>Açıklamalar

Bu nedenle yalnızca (lvalue) atama deyiminin sol tarafında kullanılabilir. Ardından, belirtilen anahtara sahip herhangi bir harita öğe varsa, yeni bir öğe oluşturulur.

Yoktur yok "sağ tarafında" (r) bu operatörü için eşdeğeri anahtar haritada bulunamamış olabilir bir olasılık olduğundan. Kullanım `Lookup` öğesi alma için üye işlevi.

### <a name="example"></a>Örnek

Örneğin bakın [CMap::Lookup](#lookup).

##  <a name="pgetfirstassoc"></a>  CMap::PGetFirstAssoc

Eşlem nesnesine ilk girişinin döndürür.

```
const CPair* PGetFirstAssoc() const;
CPair* PGetFirstAssoc();
```

### <a name="return-value"></a>Dönüş Değeri

Eşlem içindeki ilk giriş işaretçisi; bkz: [CMap::CPair](#cpair). Eşleme girdisi yok içeriyorsa değer NULL olur.

### <a name="remarks"></a>Açıklamalar

Bir işaretçi ilk öğeyi harita nesneyi döndürmek için bu işlevi çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#59](../../mfc/codesnippet/cpp/cmap-class_4.cpp)]

##  <a name="pgetnextassoc"></a>  CMap::PGetNextAssoc

İşaret ettiği harita öğesini alır. *pAssocRec*.

```
const CPair *PGetNextAssoc(const CPair* pAssocRet) const;

CPair *PGetNextAssoc(const CPair* pAssocRet);
```

### <a name="parameters"></a>Parametreler

*pAssocRet*<br/>
Bir önceki tarafından döndürülen bir eşleme girişi işaret [PGetNextAssoc](#pgetnextassoc) veya [CMap::PGetFirstAssoc](#pgetfirstassoc) çağırın.

### <a name="return-value"></a>Dönüş Değeri

Eşlem içindeki sonraki giriş işaretçisi; bkz: [CMap::CPair](#cpair). Eşlem içindeki son öğesi ise değer NULL olur.

### <a name="remarks"></a>Açıklamalar

Eşlem içindeki tüm öğeleri arasında yineleme yapmak için bu yöntemi çağırın. İlk öğe ile bir çağrı almak `PGetFirstAssoc` ve art arda çağrılar haritayla yinelemek `PGetNextAssoc`.

### <a name="example"></a>Örnek

Örneğin bakın [CMap::PGetFirstAssoc](#pgetfirstassoc).

##  <a name="plookup"></a>  CMap::PLookup

Belirli bir anahtar ile eşlenen değeri bulur.

```
const CPair* PLookup(ARG_KEY key) const;
CPair* PLookup(ARG_KEY key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak öğenin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Bir anahtar yapıya bir işaretçi; bkz: [CMap::CPair](#cpair). Eşleşme bulunursa `CMap::PLookup` NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Verilen anahtara tam olarak eşleşen bir anahtara bir eşleme öğeyi aramak için bu yöntemi çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#60](../../mfc/codesnippet/cpp/cmap-class_5.cpp)]

##  <a name="removeall"></a>  CMap::RemoveAll

Tüm değerlerin genel yardımcı işlevini çağırarak bu eşlemden kaldırır. `DestructElements`.

```
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

Eşleme zaten boşsa, işlev düzgün çalışır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#61](../../mfc/codesnippet/cpp/cmap-class_6.cpp)]

##  <a name="removekey"></a>  CMap::RemoveKey

Sağlanan anahtara karşılık gelen eşleme girişi arar; Ardından, anahtar bulunursa, giriş kaldırır.

```
BOOL RemoveKey(ARG_KEY key);
```

### <a name="parameters"></a>Parametreler

*ARG_KEY*<br/>
Anahtar türünü belirten bir şablon parametre.

*anahtar*<br/>
Kaldırılacak öğenin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Giriş bulundu ve başarıyla kaldırıldı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

`DestructElements` Yardımcı işlevini girdisini kaldırmak için kullanılır.

### <a name="example"></a>Örnek

Örneğin bakın [CMap::SetAt](#setat).

##  <a name="setat"></a>  CMap::SetAt

Bir eşlem içinde bir öğe eklemek birincil anlamına gelir.

```
void SetAt(ARG_KEY key, ARG_VALUE newValue);
```

### <a name="parameters"></a>Parametreler

*ARG_KEY*<br/>
Şablon parametresinin türünü belirleyen *anahtar* parametresi.

*anahtar*<br/>
Yeni öğenin anahtarını belirtir.

*ARG_VALUE*<br/>
Şablon parametresinin türünü belirleyen *newValue* parametresi.

*newValue*<br/>
Yeni öğenin değerini belirtir.

### <a name="remarks"></a>Açıklamalar

İlk olarak, anahtar aranır. Anahtar bulunursa, karşılık gelen değeri değiştirildikten sonra; Aksi takdirde, yeni bir anahtar-değer çifti oluşturulur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#62](../../mfc/codesnippet/cpp/cmap-class_7.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek Topla](../../visual-cpp-samples.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
