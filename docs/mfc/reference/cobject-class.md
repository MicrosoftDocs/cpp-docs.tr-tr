---
title: CObject sınıfı
ms.date: 11/04/2016
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
ms.assetid: 95e9acd3-d9eb-4ac0-b52b-ca4a501a7a3a
ms.openlocfilehash: 515c4e90ee6ab77a6c7c1ae108393ea1aafb7c17
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78855331"
---
# <a name="cobject-class"></a>CObject sınıfı

Microsoft Foundation Class Kitaplığı için asıl temel sınıf.

## <a name="syntax"></a>Sözdizimi

```
class AFX_NOVTABLE CObject
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CObject:: CObject](#cobject)|Varsayılan Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CObject:: AssertValid](#assertvalid)|Bu nesnenin bütünlüğünü doğrular.|
|[CObject::D UMP](#dump)|Bu nesnenin tanılama dökümünü üretir.|
|[CObject:: GetRuntimeClass](#getruntimeclass)|Bu nesnenin sınıfına karşılık gelen `CRuntimeClass` yapısını döndürür.|
|[CObject:: IsKindOf](#iskindof)|Bu nesnenin ilişkisini belirli bir sınıfla sınar.|
|[CObject:: Iseri hale getirilebilir](#isserializable)|Bu nesnenin seri hale getirilebilir olup olmadığını görmek için sınar.|
|[CObject:: serileştirme](#serialize)|Bir arşivden/' a bir nesne yükler veya kaydeder.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CObject:: operator delete](#operator_delete)|Özel **silme** işleci.|
|[CObject:: operator New](#operator_new)|Özel **Yeni** işleç.|

## <a name="remarks"></a>Açıklamalar

Yalnızca `CFile` ve `CObList`gibi kitaplık sınıfları için değil, aynı zamanda yazdığınız sınıflar için de kök görevi görür. `CObject` aşağıdakiler dahil olmak üzere temel hizmetler sağlar

- Serileştirme desteği

- Çalışma zamanı sınıf bilgileri

- Nesne tanılama çıktısı

- Koleksiyon sınıflarıyla uyumluluk

`CObject` birden çok devralmayı desteklemediğini unutmayın. Türetilmiş sınıflarınızda yalnızca bir `CObject` taban sınıfı olabilir ve bu `CObject` hiyerarşide en solda olmalıdır. Ancak, sağ taraftaki birden fazla devralma dallarında yapıların ve `CObject`türevi olmayan sınıfların olması için izin verilir.

Sınıf uygulamanızda ve bildirimlerinde bazı isteğe bağlı makroları kullanıyorsanız, `CObject` türetmede önemli avantajlar elde edersiniz.

İlk düzey makrolar, [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic) ve [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic), sınıf adına ve hiyerarşideki konumuna çalışma zamanı erişimine izin verir. Bu, sırasıyla anlamlı tanılama dökümü sağlar.

İkinci düzey makrolar, [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) ve [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial), ilk düzey makroların tüm işlevlerini içerir ve bir nesnenin "arşive" ve bir "Arşiv" olarak "serileştirilmesi" sağlar.

Microsoft Foundation sınıflarının ve C++ sınıflarının genel olarak türeme ve `CObject`kullanma hakkında daha fazla bilgi için, bkz. CObject ve [serileştirme](../../mfc/serialization-in-mfc.md) [kullanma](../../mfc/using-cobject.md) .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CObject`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

##  <a name="assertvalid"></a>CObject:: AssertValid

Bu nesnenin bütünlüğünü doğrular.

```
virtual void AssertValid() const;
```

### <a name="remarks"></a>Açıklamalar

`AssertValid`, iç durumunu denetleyerek bu nesne üzerinde bir geçerlilik denetimi gerçekleştirir. Kitaplığın hata ayıklama sürümünde, `AssertValid` onay edebilir ve bu nedenle programı, onaylaması başarısız olan satır numarasını ve dosya adını listeleyen iletiyle sonlandırır.

Kendi sınıfınızı yazdığınızda, kendi kendinize ve sınıfınızın diğer kullanıcılarına yönelik tanılama hizmetleri sağlamak için `AssertValid` işlevini geçersiz kılmanız gerekir. Geçersiz kılınan `AssertValid`, türetilmiş sınıfa özel veri üyelerini denetlemeden önce genellikle temel sınıfının `AssertValid` işlevini çağırır.

`AssertValid` bir **const** işlevi olduğundan, test sırasında nesne durumunu değiştirmenize izin verilmez. Kendi türetilmiş sınıfınız `AssertValid` işlevleriniz özel durum eklememelidir, ancak bunun yerine geçersiz nesne verilerini algılamamaları gerekip gerekmediğini belirtir.

"Geçerlilik" tanımı nesnenin sınıfına bağlıdır. Kural olarak, işlev bir "yüzeysel denetim" gerçekleştirmelidir. Diğer bir deyişle, bir nesne diğer nesnelere işaretçiler içeriyorsa, işaretçilerin null olup olmadığını kontrol etmelidir, ancak işaretçilerin başvurduğu nesneler üzerinde geçerlilik testi gerçekleştirmemelidir.

### <a name="example"></a>Örnek

Tüm `CObject` örneklerde kullanılan `CAge` sınıfının bir listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCObjectSample#7](../../mfc/codesnippet/cpp/cobject-class_1.cpp)]

Diğer bir örnek için bkz. [Afxdoforallobeler](diagnostic-services.md#afxdoforallobjects).

##  <a name="cobject"></a>CObject:: CObject

Bu işlevler standart `CObject` oluşturuculardır.

```
CObject();
CObject(const CObject& objectSrc);
```

### <a name="parameters"></a>Parametreler

*objectSrc*<br/>
Başka bir `CObject` başvurusu

### <a name="remarks"></a>Açıklamalar

Varsayılan sürüm, türetilmiş sınıfınızın Oluşturucusu tarafından otomatik olarak çağırılır.

Sınıfınız seri hale getirilebilir ise (IMPLEMENT_SERIAL makrosunu ekler), sınıf bildirimindeki varsayılan bir oluşturucuya (bağımsız değişken içermeyen bir Oluşturucu) sahip olmanız gerekir. Varsayılan bir oluşturucuya ihtiyacınız yoksa, özel veya korumalı "boş" bir Oluşturucu bildirin. Daha fazla bilgi için, bkz. [CObject kullanma](../../mfc/using-cobject.md).

Standart C++ varsayılan sınıf kopya Oluşturucusu üye tarafından üye kopya olarak yapılır. Özel `CObject` kopya oluşturucusunun varlığı, sınıfınızın kopya Oluşturucusu gerekliyse ancak kullanılamıyorsa bir derleyici hata iletisini garanti eder. Bu nedenle, sınıfınız bu özelliği gerektiriyorsa bir kopya Oluşturucu sağlamanız gerekir.

### <a name="example"></a>Örnek

`CObject` örneklerde kullanılan `CAge` sınıfının bir listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCObjectSample#8](../../mfc/codesnippet/cpp/cobject-class_2.cpp)]

##  <a name="dump"></a>CObject::D UMP

Nesnenizin içeriğini bir [CDumpContext](../../mfc/reference/cdumpcontext-class.md) nesnesine döker.

```
virtual void Dump(CDumpContext& dc) const;
```

### <a name="parameters"></a>Parametreler

*'ye*<br/>
Döküm için tanılama döküm bağlamı, genellikle `afxDump`.

### <a name="remarks"></a>Açıklamalar

Kendi sınıfınızı yazdığınızda, kendi kendinize ve sınıfınızın diğer kullanıcılarına yönelik tanılama hizmetleri sağlamak için `Dump` işlevini geçersiz kılmanız gerekir. Geçersiz kılınan `Dump`, türetilmiş sınıfa özel veri üyelerini yazdırmadan önce genellikle temel sınıfının `Dump` işlevini çağırır. Sınıfınız `IMPLEMENT_DYNAMIC` veya IMPLEMENT_SERIAL makrosunu kullanıyorsa, `CObject::Dump` sınıf adını yazdırır.

> [!NOTE]
>  `Dump` işleviniz çıktısının sonuna bir yeni satır karakteri yazdırmamalıdır.

`Dump` çağrılar yalnızca Microsoft Foundation Class Kitaplığı hata ayıklama sürümünde anlamlı hale getirir. Koşullu derleme için **#ifdef _DEBUG**/ `#endif` deyimleri ile çağrılar, işlev bildirimleri ve işlev uygulamalarının parantez içine almanız gerekir.

`Dump` bir **const** işlevi olduğundan, döküm sırasında nesne durumunu değiştirmenize izin verilmez.

[CDumpContext ekleme (< <) işleci](../../mfc/reference/cdumpcontext-class.md#operator_lt_lt) , bir `CObject` işaretçisi eklendiğinde `Dump` çağırır.

`Dump`, nesnelerin yalnızca "çevrimdışı" dökümünü sağlar. Bir nesne listesinin dökümünü yapabilirsiniz, örneğin, nesnelerden biri listenin kendisidir, sonunda yığının taşına sahip olursunuz.

### <a name="example"></a>Örnek

Tüm `CObject` örneklerde kullanılan `CAge` sınıfının bir listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCObjectSample#9](../../mfc/codesnippet/cpp/cobject-class_3.cpp)]

##  <a name="getruntimeclass"></a>CObject:: GetRuntimeClass

Bu nesnenin sınıfına karşılık gelen `CRuntimeClass` yapısını döndürür.

```
virtual CRuntimeClass* GetRuntimeClass() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesnenin sınıfına karşılık gelen [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yapısına yönelik bir işaretçi; hiçbir koşulda **null**.

### <a name="remarks"></a>Açıklamalar

`CObject`türetilmiş her sınıf için bir `CRuntimeClass` yapısı vardır. Yapı üyeleri aşağıdaki gibidir:

- **LPCSTR m_lpszClassName** ASCII sınıf adını içeren, null ile sonlandırılmış bir dize.

- **int m_nObjectSize** Nesnenin bayt cinsinden boyutu. Nesnede, ayrılan belleği işaret eden veri üyeleri varsa, bu belleğin boyutu dahil edilmez.

- **UINT m_wSchema** Şema numarası (seri hale getirilebilir olmayan sınıflar için-1). Şema numarası açıklaması için [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) makroya bakın.

- **CObject\* (PASCAL\* m_pfnCreateObject) ()** Sınıfınızın bir nesnesini oluşturan varsayılan oluşturucuya yönelik bir işlev işaretçisi (yalnızca sınıf dinamik oluşturmayı destekliyorsa geçerlidir; aksi takdirde, **null**döndürür).

- **CRuntimeClass\* (PASCAL\* m_pfn_GetBaseClass) ()** Uygulamanız MFC 'nin AFXDLL sürümüne dinamik olarak bağlanmışsa, taban sınıfının `CRuntimeClass` yapısını döndüren işleve yönelik bir işaretçi.

- **CRuntimeClass\* m_pBaseClass** Uygulamanız MFC 'ye statik olarak bağlanmışsa, taban sınıfının `CRuntimeClass` yapısına yönelik bir işaretçi.

Bu işlev, sınıf uygulamasında [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic), [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)veya [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) makrosunun kullanılmasını gerektirir. Aksi takdirde, yanlış sonuçlar alırsınız.

### <a name="example"></a>Örnek

Tüm `CObject` örneklerde kullanılan `CAge` sınıfının bir listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCObjectSample#10](../../mfc/codesnippet/cpp/cobject-class_4.cpp)]

##  <a name="iskindof"></a>CObject:: IsKindOf

Bu nesnenin ilişkisini belirli bir sınıfla sınar.

```
BOOL IsKindOf(const CRuntimeClass* pClass) const;
```

### <a name="parameters"></a>Parametreler

*pClass*<br/>
`CObject`türetilmiş sınıfınız ile ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yapısına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Nesne sınıfa karşılık geliyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, (1) belirtilen sınıfın bir nesnesi olup olmadığını görmek için *pClass* 'ı sınar veya (2) belirtilen sınıftan türetilmiş bir sınıfın nesnesidir. Bu işlev yalnızca [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic), [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate)veya [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) makroıyla belirtilen sınıflarda çalışır.

Çok biçimlilik özelliğini erteler, C++ bu işlevi yaygın olarak kullanmayın. Bunun yerine sanal işlevleri kullanın.

### <a name="example"></a>Örnek

Tüm `CObject` örneklerde kullanılan `CAge` sınıfının bir listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCObjectSample#11](../../mfc/codesnippet/cpp/cobject-class_5.cpp)]

##  <a name="isserializable"></a>CObject:: Iseri hale getirilebilir

Bu nesnenin serileştirme için uygun olup olmadığını test eder.

```
BOOL IsSerializable() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesne seri hale getirilebiliyorsanız sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir sınıfın seri hale getirilebilir olması için, bildiriminin [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) makrosunu içermesi ve uygulamanın [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) makrosunu içermesi gerekir.

> [!NOTE]
>  Bu işlevi geçersiz kılmayın.

### <a name="example"></a>Örnek

Tüm `CObject` örneklerde kullanılan `CAge` sınıfının bir listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCObjectSample#12](../../mfc/codesnippet/cpp/cobject-class_6.cpp)]

##  <a name="operator_delete"></a>CObject:: operator delete

Kitaplığın yayın sürümü için, işleç **silme** , **New**işlecine göre ayrılan belleği serbest bırakır.

```
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

Hata ayıklama sürümünde, işleç **silme** , bellek sızıntılarını algılamak için tasarlanan bir ayırma izleme şemasına katılır.

Kod satırını kullanıyorsanız

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

bir. Bu durumda, daha sonra raporlama için dosya adını ve satır numarasını ayrılmış blokta depolayarak **Delete** 'in üçüncü sürümü kullanılacaktır. Ek parametreler sağlama konusunda endişelenmeniz gerekmez; bir makro sizin için bunu sizin yerinize gerçekleştirir.

Hata ayıklama modunda DEBUG_NEW kullanmasanız bile, yukarıda açıklanan kaynak-dosya satır numarası raporlaması olmadan sızıntı algılamayı yine de edinirsiniz.

**New** işleçlerini ve **silmeyi**geçersiz kılarsınız, bu Tanılama özelliğini Fede olursunuz.

### <a name="example"></a>Örnek

`CObject` örneklerde kullanılan `CAge` sınıfının bir listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCObjectSample#15](../../mfc/codesnippet/cpp/cobject-class_8.cpp)]

##  <a name="operator_new"></a>CObject:: operator New

Kitaplığın yayın sürümü için, **New** işleci `malloc`benzer şekilde en iyi bellek ayırmayı gerçekleştirir.

```
void* PASCAL operator new(size_t nSize);
void* PASCAL operator new(size_t, void* p);

void* PASCAL operator new(
    size_t nSize,
    LPCSTR lpszFileName,
    int nLine);
```

### <a name="remarks"></a>Açıklamalar

Hata ayıklama sürümünde, **New** işleci bellek sızıntılarını algılamak için tasarlanan bir ayırma izleme şemasına katılır.

Kod satırını kullanıyorsanız

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

bir. Daha sonra, daha sonra raporlama için dosya adını ve satır numarasını ayrılmış blokta depolayarak, ikinci **Yeni** sürümü kullanılacaktır. Ek parametreler sağlama konusunda endişelenmeniz gerekmez; bir makro sizin için bunu sizin yerinize gerçekleştirir.

Hata ayıklama modunda DEBUG_NEW kullanmasanız bile, yukarıda açıklanan kaynak-dosya satır numarası raporlaması olmadan sızıntı algılamayı yine de edinirsiniz.

> [!NOTE]
>  Bu işleci geçersiz kılarsınız, **Delete**' i de geçersiz kılmanız gerekir. Standart Kitaplık `_new_handler` işlevini kullanmayın.

### <a name="example"></a>Örnek

`CObject` örneklerde kullanılan `CAge` sınıfının bir listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCObjectSample#16](../../mfc/codesnippet/cpp/cobject-class_9.h)]

##  <a name="serialize"></a>CObject:: serileştirme

Bu nesneyi veya bir arşivden okur veya yazar.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*<br/>
Seri hale getirilecek bir `CArchive` nesnesi.

### <a name="remarks"></a>Açıklamalar

Serileştirme işlemini planladığınız her sınıf için `Serialize` geçersiz kılmanız gerekir. Geçersiz kılınan `Serialize` önce temel sınıfının `Serialize` işlevini çağırması gerekir.

Sınıf bildirimindeki [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) makrosunu da kullanmanız ve uygulamadaki [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) makrosunu kullanmanız gerekir.

Arşivin yüklenip depolanmadığını öğrenmek için [CArchive:: ısyüklenmekte](../../mfc/reference/carchive-class.md#isloading) veya [CArchive:: ısdepokullanın](../../mfc/reference/carchive-class.md#isstoring) .

`Serialize` [CArchive:: ReadObject](../../mfc/reference/carchive-class.md#readobject) ve [CArchive:: WriteObject](../../mfc/reference/carchive-class.md#writeobject)tarafından çağırılır. Bu işlevler `CArchive` ekleme işleci ( **<\<** ) ve ayıklama işleci ( **>>** ) ile ilişkilendirilir.

Serileştirme örnekleri için bkz. [serileştirme: bir nesneyi seri hale getirme](../../mfc/serialization-serializing-an-object.md).

### <a name="example"></a>Örnek

Tüm `CObject` örneklerde kullanılan `CAge` sınıfının bir listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCObjectSample#13](../../mfc/codesnippet/cpp/cobject-class_10.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
