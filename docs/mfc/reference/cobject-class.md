---
description: 'Daha fazla bilgi edinin: CObject sınıfı'
title: CObject sınıfı
ms.date: 1/12/2021
f1_keywords:
- CObject
- AFX/CObject
- AFX/CObject::CObject
- AFX/CObject::AssertValid
- AFX/CObject::Dump
- AFX/CObject::GetRuntimeClass
- AFX/CObject::IsKindOf
- AFX/CObject::IsSerializable
- AFX/CObject::Serialize
helpviewer_keywords:
- CObject [MFC], CObject
- CObject [MFC], AssertValid
- CObject [MFC], Dump
- CObject [MFC], GetRuntimeClass
- CObject [MFC], IsKindOf
- CObject [MFC], IsSerializable
- CObject [MFC], Serialize
ms.openlocfilehash: ba152a9cbbe6e2fa217d6c2e24d13ea48dd37c87
ms.sourcegitcommit: b51f79b5394e12cd90cb65c85cc01716f90bfc90
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2021
ms.locfileid: "98167014"
---
# <a name="cobject-class"></a>`CObject` Sınıfı

Microsoft Foundation Class Kitaplığı için asıl temel sınıf.

## <a name="syntax"></a>Sözdizimi

```cpp
class AFX_NOVTABLE CObject
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[`CObject::CObject`](#cobject)|Varsayılan Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[`CObject::AssertValid`](#assertvalid)|Bu nesnenin bütünlüğünü doğrular.|
|[`CObject::Dump`](#dump)|Bu nesnenin tanılama dökümünü üretir.|
|[`CObject::GetRuntimeClass`](#getruntimeclass)|`CRuntimeClass`Bu nesnenin sınıfına karşılık gelen yapıyı döndürür.|
|[`CObject::IsKindOf`](#iskindof)|Bu nesnenin ilişkisini belirli bir sınıfla sınar.|
|[`CObject::IsSerializable`](#isserializable)|Bu nesnenin seri hale getirilebilir olup olmadığını görmek için sınar.|
|[`CObject::Serialize`](#serialize)|Bir arşivden/' a bir nesne yükler veya kaydeder.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[`CObject::operator delete`](#operator_delete)|Özel **`delete`** işleç.|
|[`CObject::operator new`](#operator_new)|Özel **`new`** işleç.|

## <a name="remarks"></a>Açıklamalar

Kök görevi yalnızca ve gibi kitaplık sınıfları için değil `CFile` `CObList` , yazdığınız sınıflar için de kullanılır. `CObject` Aşağıdakiler dahil olmak üzere temel hizmetler sağlar

- Serileştirme desteği
- Çalışma zamanı sınıf bilgileri
- Nesne tanılama çıktısı
- Koleksiyon sınıflarıyla uyumluluk

`CObject` birden çok devralmayı desteklemez. Türetilmiş sınıflarınızda yalnızca bir `CObject` temel sınıf bulunabilir ve bu, `CObject` hiyerarşide en sol olmalıdır. Ancak, `CObject` sağ taraftaki birden fazla devralma dallarında yapıların ve türetilmiş olmayan sınıfların olması için izin verilir.

`CObject`Sınıf uygulamanızda ve bildirimlerinde bazı isteğe bağlı makroları kullanırsanız Türetmenin önemli avantajlarından faydalanırsınız.

İlk düzey makrolar [`DECLARE_DYNAMIC`](run-time-object-model-services.md#declare_dynamic) ve [`IMPLEMENT_DYNAMIC`](run-time-object-model-services.md#implement_dynamic) , sınıf adına ve hiyerarşideki konumuna çalışma zamanı erişimine izin verir. Bu, sırasıyla anlamlı tanılama dökümü sağlar.

İkinci düzey makrolar [`DECLARE_SERIAL`](run-time-object-model-services.md#declare_serial) ve [`IMPLEMENT_SERIAL`](run-time-object-model-services.md#implement_serial) , ilk düzey makroların tüm işlevlerini içerir ve bir nesnenin bir "Arşiv" ve bir "arşive" olmasını sağlar.

Microsoft Foundation sınıfları ve C++ sınıflarını genel ve kullanarak türetme hakkında daha fazla bilgi için `CObject` , bkz. [CObject](../../mfc/using-cobject.md) ve [serileştirme](../../mfc/serialization-in-mfc.md)kullanma.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CObject`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**`afx.h`

## <a name="cobjectassertvalid"></a><a name="assertvalid"></a> CObject:: AssertValid

Bu nesnenin bütünlüğünü doğrular.

```cpp
virtual void AssertValid() const;
```

### <a name="remarks"></a>Açıklamalar

`AssertValid` iç durumunu denetleyerek bu nesne üzerinde bir geçerlilik denetimi gerçekleştirir. Kitaplığın hata ayıklama sürümünde, onaylama `AssertValid` işlemi başarısız olabilir ve sonra, onaylaması başarısız olan satır numarasını ve dosya adını listeleyen bir iletiyle programı sonlandırabilirsiniz.

Kendi sınıfınızı yazdığınızda, kendi `AssertValid` kendinize ve sınıfınızın diğer kullanıcılarına yönelik tanılama hizmetleri sağlamak için işlevini geçersiz kılmanız gerekir. Geçersiz kılınan, `AssertValid` `AssertValid` türetilmiş sınıfa özgü veri üyelerini denetlemeden önce temel sınıfının işlevini çağırır.

`AssertValid`Bir işlev olduğundan **`const`** , test sırasında nesne durumunu değiştirmenize izin verilmez. Kendi türetilmiş sınıf `AssertValid` işlevleriniz özel durumlar oluşturmamalı, bunun yerine geçersiz nesne verilerini algılamamaları gerekip gerekmediğini belirtir.

"Geçerlilik" tanımı nesnenin sınıfına bağlıdır. Kural olarak, işlev bir "yüzeysel denetim" olmalıdır. Diğer bir deyişle, bir nesne diğer nesnelere işaretçiler içeriyorsa, işaretçilerin olup olmadığını kontrol etmelidir `NULL` , ancak işaretçilerin başvurduğu nesneler üzerinde geçerlilik testi yapmamalıdır.

### <a name="example"></a>Örnek

[`CObList::CObList`](../../mfc/reference/coblist-class.md#coblist) `CAge` Tüm örneklerde kullanılan sınıfın listesi için bkz `CObject` ..

[!code-cpp[NVC_MFCCObjectSample#7](../../mfc/codesnippet/cpp/cobject-class_1.cpp)]

Başka bir örnek için bkz [`AfxDoForAllObjects`](diagnostic-services.md#afxdoforallobjects) ..

## <a name="cobjectcobject"></a><a name="cobject"></a> CObject:: CObject

Bu işlevler standart `CObject` oluşturuculardır.

```cpp
CObject();
CObject(const CObject& objectSrc);
```

### <a name="parameters"></a>Parametreler

*objectSrc*\
Başka bir başvuru `CObject`

### <a name="remarks"></a>Açıklamalar

Varsayılan sürüm, türetilmiş sınıfınızın Oluşturucusu tarafından otomatik olarak çağırılır.

Sınıfınız seri hale getirilebilir ise ( `IMPLEMENT_SERIAL` makroyu ekler), sınıf bildirimindeki varsayılan bir oluşturucuya (bağımsız değişken içermeyen bir Oluşturucu) sahip olmanız gerekir. Varsayılan bir oluşturucuya ihtiyacınız yoksa, özel veya korumalı "boş" bir Oluşturucu bildirin. Daha fazla bilgi için bkz [. `CObject` using ](../../mfc/using-cobject.md).

Standart C++ varsayılan sınıf kopya Oluşturucusu bir üye üye kopyası yapar. Özel kopya oluşturucusunun varlığı, `CObject` sınıfınızın kopya Oluşturucusu gerekliyse ancak kullanılamıyorsa bir derleyici hata iletisi sağlar. Sınıfınız bu özelliği gerektiriyorsa bir kopya Oluşturucu sağlayın.

### <a name="example"></a>Örnek

[`CObList::CObList`](../../mfc/reference/coblist-class.md#coblist)Örneklerde kullanılan sınıfın listesi için bkz `CAge` `CObject` ..

[!code-cpp[NVC_MFCCObjectSample#8](../../mfc/codesnippet/cpp/cobject-class_2.cpp)]

## <a name="cobjectdump"></a><a name="dump"></a> CObject::D UMP

Nesnenizin içeriğini bir [`CDumpContext`](../../mfc/reference/cdumpcontext-class.md) nesnesine döker.

```cpp
virtual void Dump(CDumpContext& dc) const;
```

### <a name="parameters"></a>Parametreler

*'ye*\
Döküm için tanılama döküm bağlamı, genellikle `afxDump` .

### <a name="remarks"></a>Açıklamalar

Kendi sınıfınızı yazdığınızda, kendi `Dump` kendinize ve sınıfınızın diğer kullanıcılarına yönelik tanılama hizmetleri sağlamak için işlevini geçersiz kılmanız gerekir. Geçersiz kılınan, `Dump` `Dump` türetilmiş sınıfa özel veri üyelerini yazdırmadan önce genellikle kendi temel sınıfının işlevini çağırır. `CObject::Dump` sınıfınız veya makrosunu kullanıyorsa, sınıf adını yazdırır `IMPLEMENT_DYNAMIC` `IMPLEMENT_SERIAL` .

> [!NOTE]
> `Dump`İşleviniz çıktısının sonuna bir yeni satır karakteri yazdırmamalıdır.

`Dump` çağrılar yalnızca Microsoft Foundation Class Kitaplığı hata ayıklama sürümünde anlamlı hale getirir. `#ifdef _DEBUG` `#endif` Koşullu derleme için deyimlerle birlikte çağrılar, işlev bildirimleri ve işlev uygulamalarının parantez içine alınmalıdır.

`Dump`Bir işlev olduğundan **`const`** , döküm sırasında nesne durumunu değiştirmenize izin verilmez.

Bir işaretçi eklendiğinde [ `CDumpContext` ekleme (<<) işleci](../../mfc/reference/cdumpcontext-class.md#operator_lt_lt) çağırır `Dump` `CObject` .

`Dump` nesnelerin yalnızca "Çevrimsiz" dökümünü sağlar. Bir nesne listesinin dökümünü yapabilirsiniz, örneğin, nesnelerden biri listenin kendisidir, sonunda yığının taşına sahip olursunuz.

### <a name="example"></a>Örnek

[`CObList::CObList`](../../mfc/reference/coblist-class.md#coblist) `CAge` Tüm örneklerde kullanılan sınıfın listesi için bkz `CObject` ..

[!code-cpp[NVC_MFCCObjectSample#9](../../mfc/codesnippet/cpp/cobject-class_3.cpp)]

## <a name="cobjectgetruntimeclass"></a><a name="getruntimeclass"></a> CObject:: GetRuntimeClass

`CRuntimeClass`Bu nesnenin sınıfına karşılık gelen yapıyı döndürür.

```cpp
virtual CRuntimeClass* GetRuntimeClass() const;
```

### <a name="return-value"></a>Dönüş Değeri

[`CRuntimeClass`](../../mfc/reference/cruntimeclass-structure.md)Bu nesnenin sınıfına karşılık gelen yapıya yönelik bir işaretçi; hiçbir şekilde **`NULL`** .

### <a name="remarks"></a>Açıklamalar

`CRuntimeClass`Her türetilmiş sınıf için bir yapı vardır `CObject` . Yapı üyeleri aşağıdaki gibidir:

- **`LPCSTR m_lpszClassName`** ASCII sınıf adını içeren, null ile sonlandırılmış bir dize.
- **`int m_nObjectSize`** Nesnenin bayt cinsinden boyutu. Nesnede, ayrılan belleği işaret eden veri üyeleri varsa, bu belleğin boyutu dahil değildir.
- **`UINT m_wSchema`** Şema numarası (seri hale getirilebilir olmayan sınıflar için-1). [`IMPLEMENT_SERIAL`](run-time-object-model-services.md#implement_serial)Şema numarası açıklaması için makroya bakın.

- **`CObject* (PASCAL* m_pfnCreateObject)()`** Sınıfınızın bir nesnesini oluşturan varsayılan oluşturucuya yönelik bir işlev işaretçisi (yalnızca sınıf dinamik oluşturmayı destekliyorsa geçerlidir; aksi takdirde, döndürür **`NULL`** ).

- **`CRuntimeClass* (PASCAL* m_pfn_GetBaseClass )()`** Uygulamanız MFC 'nin AFXDLL sürümüne dinamik olarak bağlanmışsa, taban sınıfının yapısını döndüren işleve yönelik bir işaretçi `CRuntimeClass` .

- **`CRuntimeClass* m_pBaseClass`** Uygulamanız MFC 'ye statik olarak bağlanmışsa, taban sınıfının yapısına yönelik bir işaretçi `CRuntimeClass` .

Bu işlev [`IMPLEMENT_DYNAMIC`](run-time-object-model-services.md#implement_dynamic) , sınıf uygulamasında,, [`IMPLEMENT_DYNCREATE`](run-time-object-model-services.md#implement_dyncreate) veya makrosunun kullanılmasını gerektirir [`IMPLEMENT_SERIAL`](run-time-object-model-services.md#implement_serial) . Aksi halde yanlış sonuçlar alırsınız.

### <a name="example"></a>Örnek

[`CObList::CObList`](../../mfc/reference/coblist-class.md#coblist) `CAge` Tüm örneklerde kullanılan sınıfın listesi için bkz `CObject` ..

[!code-cpp[NVC_MFCCObjectSample#10](../../mfc/codesnippet/cpp/cobject-class_4.cpp)]

## <a name="cobjectiskindof"></a><a name="iskindof"></a> CObject:: IsKindOf

Bu nesnenin ilişkisini belirli bir sınıfla sınar.

```cpp
BOOL IsKindOf(const CRuntimeClass* pClass) const;
```

### <a name="parameters"></a>Parametreler

*`pClass`*\
[`CRuntimeClass`](../../mfc/reference/cruntimeclass-structure.md)Türetilmiş sınıfınız ile ilişkili bir yapıya yönelik işaretçi `CObject` .

### <a name="return-value"></a>Dönüş Değeri

Nesne sınıfa karşılık geliyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev *`pClass`* , (1) belirtilen sınıftan bir nesne mi yoksa (2) belirtilen sınıftan türetilmiş bir sınıfın nesnesi mi olduğunu görmek için sınar. Bu işlev yalnızca [`DECLARE_DYNAMIC`](run-time-object-model-services.md#declare_dynamic) ,, [`DECLARE_DYNCREATE`](run-time-object-model-services.md#declare_dyncreate) veya makroyla belirtilen sınıflarda çalışır [`DECLARE_SERIAL`](run-time-object-model-services.md#declare_serial) .

C++ çok biçimlilik özelliğini erteler olduğundan bu işlevi çok yaygın kullanmayın. Bunun yerine sanal işlevleri kullanın.

### <a name="example"></a>Örnek

[`CObList::CObList`](../../mfc/reference/coblist-class.md#coblist) `CAge` Tüm örneklerde kullanılan sınıfın listesi için bkz `CObject` ..

[!code-cpp[NVC_MFCCObjectSample#11](../../mfc/codesnippet/cpp/cobject-class_5.cpp)]

## <a name="cobjectisserializable"></a><a name="isserializable"></a> CObject:: Iseri hale getirilebilir

Bu nesnenin serileştirme için uygun olup olmadığını test eder.

```cpp
BOOL IsSerializable() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesne seri hale getirilebiliyorsanız sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir sınıfın seri hale getirilebilir olması için, bildiriminin [`DECLARE_SERIAL`](run-time-object-model-services.md#declare_serial) makroyu içermesi ve uygulamanın makroyu içermesi gerekir [`IMPLEMENT_SERIAL`](run-time-object-model-services.md#implement_serial) .

> [!NOTE]
> Bu işlevi geçersiz kılmayın.

### <a name="example"></a>Örnek

[`CObList::CObList`](../../mfc/reference/coblist-class.md#coblist) `CAge` Tüm örneklerde kullanılan sınıfın listesi için bkz `CObject` ..

[!code-cpp[NVC_MFCCObjectSample#12](../../mfc/codesnippet/cpp/cobject-class_6.cpp)]

## <a name="cobjectoperator-delete"></a><a name="operator_delete"></a> CObject:: operator delete

Kitaplığın yayın sürümü için işleç, **`delete`** işleç tarafından ayrılan belleği serbest bırakır **`new`** .

```cpp
void PASCAL operator delete(void* p);

void PASCAL operator delete(
    void* p,
    void* pPlace);

void PASCAL operator delete(
    void* p,
    LPCSTR lpszFileName,
    int nLine);
```

### <a name="remarks"></a>Açıklamalar

Hata ayıklama sürümünde operatör, **`delete`** bellek sızıntılarını algılamak için tasarlanan bir ayırma izleme şemasına katılır.

Kod satırını kullanıyorsanız

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

bir. Daha sonra, **`delete`** daha sonra raporlama için dosya adını ve satır numarasını ayrılmış blokta depolayarak üçüncü sürümü kullanılacaktır. Ek parametreler sağlamaya endişelenmeniz gerekmez; bir makro sizin için bunu sizin yerinize gerçekleştirir.

`DEBUG_NEW`Hata ayıklama modunda kullanmasanız bile, yukarıda açıklanan kaynak-dosya satır numarası raporlaması olmadan sızıntı algılamayı yine de edinirsiniz.

İşleçlerini ve işlecini geçersiz kılarsınız **`new`** **`delete`** , bu Tanılama özelliğini yasakladıysanız.

### <a name="example"></a>Örnek

[`CObList::CObList`](../../mfc/reference/coblist-class.md#coblist)Örneklerde kullanılan sınıfın listesi için bkz `CAge` `CObject` ..

[!code-cpp[NVC_MFCCObjectSample#15](../../mfc/codesnippet/cpp/cobject-class_8.cpp)]

## <a name="cobjectoperator-new"></a><a name="operator_new"></a> CObject:: operator New

Kitaplığın yayın sürümü için, işleci **`new`** Şuna benzer bir şekilde en iyi bellek ayırmayı yapar `malloc` .

```cpp
void* PASCAL operator new(size_t nSize);
void* PASCAL operator new(size_t, void* p);

void* PASCAL operator new(
    size_t nSize,
    LPCSTR lpszFileName,
    int nLine);
```

### <a name="remarks"></a>Açıklamalar

Hata ayıklama sürümünde operatör, **`new`** bellek sızıntılarını algılamak için tasarlanan bir ayırma izleme şemasına katılır.

Kod satırını kullanıyorsanız

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

bir. Daha sonra, **`new`** daha sonra raporlama için dosya adını ve satır numarasını ayrılmış blokta depolayarak ikinci sürümü kullanılır. Ek parametreler sağlamaya endişelenmeniz gerekmez; bir makro sizin için bunu sizin yerinize gerçekleştirir.

`DEBUG_NEW`Hata ayıklama modunda kullanmasanız bile, yukarıda açıklanan kaynak-dosya satır numarası raporlaması olmadan sızıntı algılamayı yine de edinirsiniz.

> [!NOTE]
> Bu işleci geçersiz kılarsınız ayrıca geçersiz kılmanız gerekir **`delete`** . Standart Kitaplık `_new_handler` işlevini kullanmayın.

### <a name="example"></a>Örnek

[`CObList::CObList`](../../mfc/reference/coblist-class.md#coblist)Örneklerde kullanılan sınıfın listesi için bkz `CAge` `CObject` ..

[!code-cpp[NVC_MFCCObjectSample#16](../../mfc/codesnippet/cpp/cobject-class_9.h)]

## <a name="cobjectserialize"></a><a name="serialize"></a> CObject:: serileştirme

Bu nesneyi veya bir arşivden okur veya yazar.

```cpp
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*`ar`*\
`CArchive`Seri hale getirilecek bir nesne.

### <a name="remarks"></a>Açıklamalar

`Serialize`Serileştirme işlemini planladığınız her sınıf için geçersiz kılın. Geçersiz kılınan, `Serialize` önce `Serialize` temel sınıfının işlevini çağırmalıdır.

Ayrıca, [`DECLARE_SERIAL`](run-time-object-model-services.md#declare_serial) sınıf bildirimindeki makroyu kullanmanız ve bu makroyu uygulamada kullanmanız gerekir [`IMPLEMENT_SERIAL`](run-time-object-model-services.md#implement_serial) .

[`CArchive::IsLoading`](../../mfc/reference/carchive-class.md#isloading) [`CArchive::IsStoring`](../../mfc/reference/carchive-class.md#isstoring) Arşivin yüklenip yüklenmediğini veya depolanmadığını öğrenmek için veya kullanın.

`Serialize` , ve tarafından [`CArchive::ReadObject`](../../mfc/reference/carchive-class.md#readobject) çağırılır [`CArchive::WriteObject`](../../mfc/reference/carchive-class.md#writeobject) . Bu işlevler, `CArchive` ekleme işleci ( **`<<`** ) ve ayıklama işleci () ile ilişkilendirilir **`>>`** .

Serileştirme örnekleri için, [bir nesneyi seri hale](../../mfc/serialization-serializing-an-object.md)getirme makalesine bakın.

### <a name="example"></a>Örnek

[`CObList::CObList`](../../mfc/reference/coblist-class.md#coblist) `CAge` Tüm örneklerde kullanılan sınıfın listesi için bkz `CObject` ..

[!code-cpp[NVC_MFCCObjectSample#13](../../mfc/codesnippet/cpp/cobject-class_10.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
