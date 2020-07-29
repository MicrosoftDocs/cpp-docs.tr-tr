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
ms.openlocfilehash: ce745e0717e36a3c9acb5323d04545c59750add7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222907"
---
# <a name="cobject-class"></a>CObject sınıfı

Microsoft Foundation Class Kitaplığı için asıl temel sınıf.

## <a name="syntax"></a>Sözdizimi

```
class AFX_NOVTABLE CObject
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CObject:: CObject](#cobject)|Varsayılan Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CObject:: AssertValid](#assertvalid)|Bu nesnenin bütünlüğünü doğrular.|
|[CObject::D UMP](#dump)|Bu nesnenin tanılama dökümünü üretir.|
|[CObject:: GetRuntimeClass](#getruntimeclass)|`CRuntimeClass`Bu nesnenin sınıfına karşılık gelen yapıyı döndürür.|
|[CObject:: IsKindOf](#iskindof)|Bu nesnenin ilişkisini belirli bir sınıfla sınar.|
|[CObject:: Iseri hale getirilebilir](#isserializable)|Bu nesnenin seri hale getirilebilir olup olmadığını görmek için sınar.|
|[CObject:: serileştirme](#serialize)|Bir arşivden/' a bir nesne yükler veya kaydeder.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CObject:: operator delete](#operator_delete)|Özel **`delete`** işleç.|
|[CObject:: operator New](#operator_new)|Özel **`new`** işleç.|

## <a name="remarks"></a>Açıklamalar

Kök görevi yalnızca ve gibi kitaplık sınıfları için değil `CFile` `CObList` , yazdığınız sınıflar için de kullanılır. `CObject`Aşağıdakiler dahil olmak üzere temel hizmetler sağlar

- Serileştirme desteği

- Çalışma zamanı sınıf bilgileri

- Nesne tanılama çıktısı

- Koleksiyon sınıflarıyla uyumluluk

`CObject`Birden çok devralmayı desteklemediğine unutmayın. Türetilmiş sınıflarınızda yalnızca bir `CObject` temel sınıf bulunabilir ve bu, `CObject` hiyerarşide en sol olmalıdır. Ancak, `CObject` sağ taraftaki birden fazla devralma dallarında yapıların ve türetilmiş olmayan sınıfların olması için izin verilir.

`CObject`Sınıf uygulamanızda ve bildirimlerinde bazı isteğe bağlı makroları kullanırsanız Türetmenin önemli avantajlarından faydalanırsınız.

İlk düzey makrolar, [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic) ve [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic), sınıf adına ve hiyerarşideki konumuna çalışma zamanı erişimine izin verir. Bu, sırasıyla anlamlı tanılama dökümü sağlar.

İkinci düzey makrolar, [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) ve [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial), ilk düzey makroların tüm işlevlerini içerir ve bir nesnenin "arşive" ve bir "Arşiv" olarak "serileştirilmesi" sağlar.

Microsoft Foundation sınıfları ve C++ sınıflarını genel ve kullanarak türetme hakkında daha fazla bilgi için `CObject` , bkz. [CObject](../../mfc/using-cobject.md) ve [serileştirme](../../mfc/serialization-in-mfc.md)kullanma.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CObject`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="cobjectassertvalid"></a><a name="assertvalid"></a>CObject:: AssertValid

Bu nesnenin bütünlüğünü doğrular.

```
virtual void AssertValid() const;
```

### <a name="remarks"></a>Açıklamalar

`AssertValid`iç durumunu denetleyerek bu nesne üzerinde bir geçerlilik denetimi gerçekleştirir. Kitaplığın hata ayıklama sürümünde, `AssertValid` onay olabilir ve bu nedenle programı, onaylaması başarısız olan satır numarasını ve dosya adını listeleyen iletiyle sonlandırır.

Kendi sınıfınızı yazdığınızda, kendi `AssertValid` kendinize ve sınıfınızın diğer kullanıcılarına yönelik tanılama hizmetleri sağlamak için işlevini geçersiz kılmanız gerekir. Geçersiz kılınan, `AssertValid` `AssertValid` türetilmiş sınıfa özgü veri üyelerini denetlemeden önce temel sınıfının işlevini çağırır.

`AssertValid`Bir işlev olduğundan **`const`** , test sırasında nesne durumunu değiştirmenize izin verilmez. Kendi türetilmiş sınıf `AssertValid` işlevleriniz özel durum eklememelidir, ancak bunun yerine geçersiz nesne verilerini algılamamaları gerekip gerekmediğini belirtir.

"Geçerlilik" tanımı nesnenin sınıfına bağlıdır. Kural olarak, işlev bir "yüzeysel denetim" gerçekleştirmelidir. Diğer bir deyişle, bir nesne diğer nesnelere işaretçiler içeriyorsa, işaretçilerin null olup olmadığını kontrol etmelidir, ancak işaretçilerin başvurduğu nesneler üzerinde geçerlilik testi gerçekleştirmemelidir.

### <a name="example"></a>Örnek

Tüm örneklerde kullanılan sınıfın listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) `CAge` `CObject` .

[!code-cpp[NVC_MFCCObjectSample#7](../../mfc/codesnippet/cpp/cobject-class_1.cpp)]

Diğer bir örnek için bkz. [Afxdoforallobeler](diagnostic-services.md#afxdoforallobjects).

## <a name="cobjectcobject"></a><a name="cobject"></a>CObject:: CObject

Bu işlevler standart `CObject` oluşturuculardır.

```
CObject();
CObject(const CObject& objectSrc);
```

### <a name="parameters"></a>Parametreler

*objectSrc*<br/>
Başka bir başvuru`CObject`

### <a name="remarks"></a>Açıklamalar

Varsayılan sürüm, türetilmiş sınıfınızın Oluşturucusu tarafından otomatik olarak çağırılır.

Sınıfınız seri hale getirilebilir ise (IMPLEMENT_SERIAL makrosunu ekler), sınıf bildirimindeki varsayılan bir oluşturucuya (bağımsız değişken içermeyen bir Oluşturucu) sahip olmanız gerekir. Varsayılan bir oluşturucuya ihtiyacınız yoksa, özel veya korumalı "boş" bir Oluşturucu bildirin. Daha fazla bilgi için, bkz. [CObject kullanma](../../mfc/using-cobject.md).

Standart C++ varsayılan sınıf kopya Oluşturucusu bir üye üye kopyası yapar. Özel kopya oluşturucusunun varlığı, `CObject` sınıfınızın kopya Oluşturucusu gerekliyse ancak kullanılamıyorsa bir derleyici hata iletisi sağlar. Bu nedenle, sınıfınız bu özelliği gerektiriyorsa bir kopya Oluşturucu sağlamanız gerekir.

### <a name="example"></a>Örnek

Örneklerde kullanılan sınıfın listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) `CAge` `CObject` .

[!code-cpp[NVC_MFCCObjectSample#8](../../mfc/codesnippet/cpp/cobject-class_2.cpp)]

## <a name="cobjectdump"></a><a name="dump"></a>CObject::D UMP

Nesnenizin içeriğini bir [CDumpContext](../../mfc/reference/cdumpcontext-class.md) nesnesine döker.

```
virtual void Dump(CDumpContext& dc) const;
```

### <a name="parameters"></a>Parametreler

*'ye*<br/>
Döküm için tanılama döküm bağlamı, genellikle `afxDump` .

### <a name="remarks"></a>Açıklamalar

Kendi sınıfınızı yazdığınızda, kendi `Dump` kendinize ve sınıfınızın diğer kullanıcılarına yönelik tanılama hizmetleri sağlamak için işlevini geçersiz kılmanız gerekir. Geçersiz kılınan, `Dump` `Dump` türetilmiş sınıfa özel veri üyelerini yazdırmadan önce genellikle kendi temel sınıfının işlevini çağırır. `CObject::Dump`sınıfınız veya IMPLEMENT_SERIAL makrosunu kullanıyorsa, sınıf adını yazdırır `IMPLEMENT_DYNAMIC` .

> [!NOTE]
> `Dump`İşleviniz çıktısının sonuna bir yeni satır karakteri yazdırmamalıdır.

`Dump`çağrılar yalnızca Microsoft Foundation Class Kitaplığı hata ayıklama sürümünde anlamlı hale getirir. Koşullu derleme için **#ifdef _debug** /  deyimleriyle çağrılar, işlev bildirimleri ve işlev uygulamalarının parantez içine almanız gerekir `#endif` .

`Dump`Bir işlev olduğundan **`const`** , döküm sırasında nesne durumunu değiştirmenize izin verilmez.

[CDumpContext ekleme (<<) işleci](../../mfc/reference/cdumpcontext-class.md#operator_lt_lt) `Dump` bir `CObject` işaretçi eklendiğinde çağırır.

`Dump`nesnelerin yalnızca "Çevrimsiz" dökümünü sağlar. Bir nesne listesinin dökümünü yapabilirsiniz, örneğin, nesnelerden biri listenin kendisidir, sonunda yığının taşına sahip olursunuz.

### <a name="example"></a>Örnek

Tüm örneklerde kullanılan sınıfın listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) `CAge` `CObject` .

[!code-cpp[NVC_MFCCObjectSample#9](../../mfc/codesnippet/cpp/cobject-class_3.cpp)]

## <a name="cobjectgetruntimeclass"></a><a name="getruntimeclass"></a>CObject:: GetRuntimeClass

`CRuntimeClass`Bu nesnenin sınıfına karşılık gelen yapıyı döndürür.

```
virtual CRuntimeClass* GetRuntimeClass() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesnenin sınıfına karşılık gelen [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yapısına yönelik bir işaretçi; hiçbir koşulda **null**.

### <a name="remarks"></a>Açıklamalar

`CRuntimeClass`Her türetilmiş sınıf için bir yapı vardır `CObject` . Yapı üyeleri aşağıdaki gibidir:

- **LPCSTR m_lpszClassName** ASCII sınıf adını içeren, null ile sonlandırılmış bir dize.

- **int m_nObjectSize** Nesnenin bayt cinsinden boyutu. Nesnede, ayrılan belleği işaret eden veri üyeleri varsa, bu belleğin boyutu dahil edilmez.

- **UINT m_wSchema** Şema numarası (seri hale getirilebilir olmayan sınıflar için-1). Şema numarası açıklaması için [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) makroya bakın.

- **CObject \* (Pascal \* m_pfnCreateObject) ()** sınıfınızın bir nesnesini oluşturan varsayılan oluşturucuya yönelik bir işlev işaretçisi (yalnızca sınıf dinamik oluşturmayı destekliyorsa geçerlidir; aksi takdirde, **null**döndürür).

- Uygulamanız MFC 'nin AFXDLL sürümüne dinamik olarak bağlanmışsa, temel sınıfın yapısını döndüren işlevin işaretçisi olan **CRuntimeClass \* (Pascal \* m_pfn_GetBaseClass) ()** `CRuntimeClass` .

- Uygulamanız MFC 'ye statik olarak bağlanmışsa, temel sınıfın yapısına yönelik bir işaretçi olan **CRuntimeClass \* m_pBaseClass** `CRuntimeClass` .

Bu işlev, sınıf uygulamasında [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic), [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)veya [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) makrosunun kullanılmasını gerektirir. Aksi takdirde, yanlış sonuçlar alırsınız.

### <a name="example"></a>Örnek

Tüm örneklerde kullanılan sınıfın listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) `CAge` `CObject` .

[!code-cpp[NVC_MFCCObjectSample#10](../../mfc/codesnippet/cpp/cobject-class_4.cpp)]

## <a name="cobjectiskindof"></a><a name="iskindof"></a>CObject:: IsKindOf

Bu nesnenin ilişkisini belirli bir sınıfla sınar.

```
BOOL IsKindOf(const CRuntimeClass* pClass) const;
```

### <a name="parameters"></a>Parametreler

*pClass*<br/>
Türetilmiş sınıfınız ile ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yapısına yönelik bir işaretçi `CObject` .

### <a name="return-value"></a>Dönüş Değeri

Nesne sınıfa karşılık geliyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, (1) belirtilen sınıfın bir nesnesi olup olmadığını görmek için *pClass* 'ı sınar veya (2) belirtilen sınıftan türetilmiş bir sınıfın nesnesidir. Bu işlev yalnızca [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic), [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate)veya [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) makroıyla belirtilen sınıflarda çalışır.

C++ çok biçimlilik özelliğini erteler olduğu için bu işlevi yaygın olarak kullanmayın. Bunun yerine sanal işlevleri kullanın.

### <a name="example"></a>Örnek

Tüm örneklerde kullanılan sınıfın listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) `CAge` `CObject` .

[!code-cpp[NVC_MFCCObjectSample#11](../../mfc/codesnippet/cpp/cobject-class_5.cpp)]

## <a name="cobjectisserializable"></a><a name="isserializable"></a>CObject:: Iseri hale getirilebilir

Bu nesnenin serileştirme için uygun olup olmadığını test eder.

```
BOOL IsSerializable() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesne seri hale getirilebiliyorsanız sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir sınıfın seri hale getirilebilir olması için, bildiriminin [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) makrosunu içermesi ve uygulamanın [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) makrosunu içermesi gerekir.

> [!NOTE]
> Bu işlevi geçersiz kılmayın.

### <a name="example"></a>Örnek

Tüm örneklerde kullanılan sınıfın listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) `CAge` `CObject` .

[!code-cpp[NVC_MFCCObjectSample#12](../../mfc/codesnippet/cpp/cobject-class_6.cpp)]

## <a name="cobjectoperator-delete"></a><a name="operator_delete"></a>CObject:: operator delete

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

bir. Daha sonra, **`delete`** daha sonra raporlama için dosya adını ve satır numarasını ayrılmış blokta depolayarak üçüncü sürümü kullanılacaktır. Ek parametreler sağlama konusunda endişelenmeniz gerekmez; bir makro sizin için bunu sizin yerinize gerçekleştirir.

Hata ayıklama modunda DEBUG_NEW kullanmasanız bile, yukarıda açıklanan kaynak-dosya satır numarası raporlaması olmadan sızıntı algılamayı yine de edinirsiniz.

İşleçlerini ve işlecini geçersiz kılarsınız **`new`** **`delete`** , bu Tanılama özelliğini yasakladıysanız.

### <a name="example"></a>Örnek

Örneklerde kullanılan sınıfın listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) `CAge` `CObject` .

[!code-cpp[NVC_MFCCObjectSample#15](../../mfc/codesnippet/cpp/cobject-class_8.cpp)]

## <a name="cobjectoperator-new"></a><a name="operator_new"></a>CObject:: operator New

Bu kitaplığın yayın sürümü için, işleci **`new`** Şuna benzer bir şekilde en iyi bellek ayırmayı gerçekleştirir `malloc` .

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

bir. Daha sonra, **`new`** daha sonra raporlama için dosya adını ve satır numarasını ayrılmış blokta depolayarak ikinci sürümü kullanılır. Ek parametreler sağlama konusunda endişelenmeniz gerekmez; bir makro sizin için bunu sizin yerinize gerçekleştirir.

Hata ayıklama modunda DEBUG_NEW kullanmasanız bile, yukarıda açıklanan kaynak-dosya satır numarası raporlaması olmadan sızıntı algılamayı yine de edinirsiniz.

> [!NOTE]
> Bu işleci geçersiz kılarsınız ayrıca geçersiz kılmanız gerekir **`delete`** . Standart Kitaplık `_new_handler` işlevini kullanmayın.

### <a name="example"></a>Örnek

Örneklerde kullanılan sınıfın listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) `CAge` `CObject` .

[!code-cpp[NVC_MFCCObjectSample#16](../../mfc/codesnippet/cpp/cobject-class_9.h)]

## <a name="cobjectserialize"></a><a name="serialize"></a>CObject:: serileştirme

Bu nesneyi veya bir arşivden okur veya yazar.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*<br/>
`CArchive`Seri hale getirilecek bir nesne.

### <a name="remarks"></a>Açıklamalar

`Serialize`Serileştirme işlemini planladığınız her sınıf için geçersiz kılmanız gerekir. Geçersiz kılınan, `Serialize` önce `Serialize` temel sınıfının işlevini çağırmalıdır.

Sınıf bildirimindeki [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) makrosunu da kullanmanız ve uygulamadaki [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) makrosunu kullanmanız gerekir.

Arşivin yüklenip depolanmadığını öğrenmek için [CArchive:: ısyüklenmekte](../../mfc/reference/carchive-class.md#isloading) veya [CArchive:: ısdepokullanın](../../mfc/reference/carchive-class.md#isstoring) .

`Serialize`[CArchive:: ReadObject](../../mfc/reference/carchive-class.md#readobject) ve [CArchive:: WriteObject](../../mfc/reference/carchive-class.md#writeobject)tarafından çağırılır. Bu işlevler `CArchive` ekleme işleci () ile ilişkilendirilir **<\<**) and extraction operator ( **>>** .

Serileştirme örnekleri için bkz. [serileştirme: bir nesneyi seri hale getirme](../../mfc/serialization-serializing-an-object.md).

### <a name="example"></a>Örnek

Tüm örneklerde kullanılan sınıfın listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) `CAge` `CObject` .

[!code-cpp[NVC_MFCCObjectSample#13](../../mfc/codesnippet/cpp/cobject-class_10.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
