---
title: CObject Sınıfı
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
ms.openlocfilehash: 66d76e0062d13b2bd5a16d9b07f99db9e989805a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753983"
---
# <a name="cobject-class"></a>CObject Sınıfı

Microsoft Hazırlık Sınıfı Kitaplığı için temel taban sınıf.

## <a name="syntax"></a>Sözdizimi

```
class AFX_NOVTABLE CObject
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CObject::CObject](#cobject)|Varsayılan oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CObject::AssertValid](#assertvalid)|Bu nesnenin bütünlüğünü doğrular.|
|[CObject::Dump](#dump)|Bu nesnenin tanılama dökümesini üretir.|
|[CObject::GetRuntimeClass](#getruntimeclass)|Bu `CRuntimeClass` nesnenin sınıfına karşılık gelen yapıyı döndürür.|
|[Cobject::Iskindof](#iskindof)|Bu nesnenin belirli bir sınıfla ilişkisini sınar.|
|[CObject::IsSerializable](#isserializable)|Bu nesnenin seri hale getirilip serileştirilemeyeceğini görmek için testler.|
|[CObject::Serialize](#serialize)|Bir nesneyi arşivden yükler veya depolar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CObject::operator silme](#operator_delete)|Özel **silme** işleci.|
|[CObject::operatör yeni](#operator_new)|Özel **yeni** operatör.|

## <a name="remarks"></a>Açıklamalar

Yalnızca kitaplık sınıfları için `CFile` `CObList`değil, yazdığınız sınıflar için de kök görevi görür. `CObject`dahil olmak üzere temel hizmetler sağlar

- Serileştirme desteği

- Çalışma zamanı sınıf bilgileri

- Nesne tanıçıktı

- Toplama sınıflarıyla uyumluluk

Birden `CObject` çok devralmayı desteklemediğini unutmayın. Türemiş sınıflarınızın `CObject` yalnızca bir taban `CObject` sınıfı olabilir ve bu hiyerarşide en çok sola olmalıdır. Ancak, sağ el çoklu kalıtım dallarında yapıların ve türetilmiş olmayan `CObject`sınıfların olması caizdir.

Sınıf uygulamanızda ve `CObject` bildirimlerinizde isteğe bağlı makrolardan bazılarını kullanırsanız türetmenin önemli faydalarını fark elabilirsiniz.

Birinci düzey makrolar, [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic) ve [IMPLEMENT_DYNAMIC,](run-time-object-model-services.md#implement_dynamic)sınıf adına ve hiyerarşideki konumuna çalışma zamanı erişimine izin verir. Bu da anlamlı tanısal damping sağlar.

İkinci düzey makrolar, [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) ve [IMPLEMENT_SERIAL,](run-time-object-model-services.md#implement_serial)birinci düzey makroların tüm işlevselliğini içerir ve bir nesnenin "arşive" ve "arşivden" "serihale" edilmesini sağlar.

Genel olarak Microsoft Foundation sınıflarını ve C++ sınıflarını türetme ve kullanma `CObject`hakkında bilgi için bkz. [Using CObject](../../mfc/using-cobject.md) [Serialization](../../mfc/serialization-in-mfc.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CObject`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="cobjectassertvalid"></a><a name="assertvalid"></a>CObject::AssertValid

Bu nesnenin bütünlüğünü doğrular.

```
virtual void AssertValid() const;
```

### <a name="remarks"></a>Açıklamalar

`AssertValid`iç durumunu denetleyerek bu nesne üzerinde bir geçerlilik denetimi gerçekleştirir. Kitaplığın Hata Ayıklama sürümünde, `AssertValid` iddianın başarısız olduğu satır numarasını ve dosya adını listeleyen bir iletiyle programı ileri sürebilir ve sonlandırabilir.

Kendi sınıfınızı yazarken, kendiniz ve `AssertValid` sınıfınızın diğer kullanıcıları için tanılama hizmetleri sağlamak için işlevi geçersiz kılmanız gerekir. Geçersiz kılınan `AssertValid` genellikle `AssertValid` türemiş sınıfa özgü veri üyelerini denetlemeden önce taban sınıfının işlevini çağırır.

Const bir işlev `AssertValid` olduğundan, sınama sırasında nesne durumunu değiştirmenize izin verilmez. **const** Kendi türemiş sınıf `AssertValid` işlevleri özel durumlar atmamalıdır, daha ziyade geçersiz nesne verileri algılayıp algılamadığını ileri sürmelidir.

"Geçerlilik" tanımı nesnenin sınıfına bağlıdır. Kural olarak, işlev "sığ denetim" gerçekleştirmelidir. Diğer bir deyişle, bir nesne diğer nesnelere işaretçiler içeriyorsa, işaretçilerin null olup olmadığını denetlemek gerekir, ancak işaretçiler tarafından başvurulmuyorum nesneler üzerinde geçerlilik testi gerçekleştirmemelidir.

### <a name="example"></a>Örnek

Tüm `CAge` `CObject` örneklerde kullanılan sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCObjectSample#7](../../mfc/codesnippet/cpp/cobject-class_1.cpp)]

Başka bir örnek için, [Bkz. AfxDoForAllObjects](diagnostic-services.md#afxdoforallobjects).

## <a name="cobjectcobject"></a><a name="cobject"></a>CObject::CObject

Bu işlevler `CObject` standart yapıcılardır.

```
CObject();
CObject(const CObject& objectSrc);
```

### <a name="parameters"></a>Parametreler

*nesneSrc*<br/>
Başka bir referans`CObject`

### <a name="remarks"></a>Açıklamalar

Varsayılan sürüm, türemiş sınıfınızın oluşturucusu tarafından otomatik olarak çağrılır.

Sınıfınız serileştirilebilirse (IMPLEMENT_SERIAL makroyu içeriyorsa), sınıf bildiriminizde varsayılan bir oluşturucu (bağımsız değişkeni olmayan bir oluşturucu) olmalıdır. Varsayılan bir oluşturucuya ihtiyacınız yoksa, özel veya korumalı "boş" bir oluşturucu bildirin. Daha fazla bilgi için [Bkz. CObject'i kullanma.](../../mfc/using-cobject.md)

Standart C++ varsayılan sınıf kopya oluşturucu üye kopyayapar. Özel `CObject` kopya oluşturucunun varlığı, sınıfınızın kopya oluşturucusu gerekliyse ancak kullanılamıyorsa derleyici hata iletisini garanti eder. Bu nedenle, sınıfınız bu özelliği gerektiriyorsa bir kopya oluşturucu sağlamanız gerekir.

### <a name="example"></a>Örnek

Bkz. [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) örneklerde `CAge` kullanılan sınıfın bir listesi için. `CObject`

[!code-cpp[NVC_MFCCObjectSample#8](../../mfc/codesnippet/cpp/cobject-class_2.cpp)]

## <a name="cobjectdump"></a><a name="dump"></a>CObject::Dump

Nesnenizin içeriğini [cdumpcontext](../../mfc/reference/cdumpcontext-class.md) nesnesine atar.

```
virtual void Dump(CDumpContext& dc) const;
```

### <a name="parameters"></a>Parametreler

*Dc*<br/>
Damping için tanılama `afxDump`dökümü bağlamı, genellikle .

### <a name="remarks"></a>Açıklamalar

Kendi sınıfınızı yazarken, kendiniz ve `Dump` sınıfınızın diğer kullanıcıları için tanılama hizmetleri sağlamak için işlevi geçersiz kılmanız gerekir. Geçersiz kılınan `Dump` genellikle `Dump` türemiş sınıfa özgü veri üyelerini yazdırmadan önce taban sınıfının işlevini çağırır. `CObject::Dump`sınıfınız `IMPLEMENT_DYNAMIC` makroyu veya IMPLEMENT_SERIAL kullanıyorsa sınıf adını yazdırır.

> [!NOTE]
> Işleviniz `Dump` çıktısının sonunda yeni bir satır karakteri yazdırmamalıdır.

`Dump`aramalar yalnızca Microsoft Hazırlık Sınıfı Kitaplığı'nın Hata Ayıklama sürümünde anlamlıdır. Çağrıları, işlev bildirimlerini ve işlev uygulamalarını **koşullu** /  `#endif` derleme için #ifdef _DEBUG deyimlerle parantez içinde toplamanız gerekir.

`Dump` **Const** bir işlev olduğundan, dökümü sırasında nesne durumunu değiştirmenize izin verilmez.

Bir `CObject` işaretçi takıldığında [CDumpContext ekleme (<<) işleci](../../mfc/reference/cdumpcontext-class.md#operator_lt_lt) çağırır. `Dump`

`Dump`nesnelerin sadece "asiklik" damping izin verir. Örneğin, nesnelerin listesini dökümü yapabilirsiniz, ancak nesnelerden biri listenin kendisi ise, sonunda yığını taşarsınız.

### <a name="example"></a>Örnek

Tüm `CAge` `CObject` örneklerde kullanılan sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCObjectSample#9](../../mfc/codesnippet/cpp/cobject-class_3.cpp)]

## <a name="cobjectgetruntimeclass"></a><a name="getruntimeclass"></a>CObject::GetRuntimeClass

Bu `CRuntimeClass` nesnenin sınıfına karşılık gelen yapıyı döndürür.

```
virtual CRuntimeClass* GetRuntimeClass() const;
```

### <a name="return-value"></a>Dönüş Değeri

[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yapısıiçin bir işaretçi bu nesnenin sınıfına karşılık gelen; asla **NULL**.

### <a name="remarks"></a>Açıklamalar

Her `CRuntimeClass` `CObject`türemiş sınıf için bir yapı vardır. Yapı üyeleri aşağıdaki gibidir:

- **LPCSTR m_lpszClassName** ASCII sınıf adını içeren null-sonlandırılan dize.

- **int m_nObjectSize** Nesnenin boyutu, baytlar halinde. Nesne, ayrılan belleğe işaret eden veri üyelerine sahipse, bu belleğin boyutu dahil edilmez.

- **UINT m_wSchema** Şema numarası ( - 1 seri olmayan sınıflar için). Şema numarasının açıklaması için [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) makroya bakın.

- **CObject\* (\* PASCAL m_pfnCreateObject )( )** Varsayılan oluşturucuya sınıfınızın bir nesnesini oluşturan bir işlev işaretçisi (yalnızca sınıf dinamik oluşturmayı destekliyorsa geçerlidir; aksi takdirde **NULL**döndürür).

- **CRuntimeClass\* (\* PASCAL m_pfn_GetBaseClass )( )** Uygulamanız MFC'nin AFXDLL sürümüne dinamik olarak `CRuntimeClass` bağlıysa, taban sınıfın yapısını döndüren bir işlevin işaretçisi.

- **CRuntimeClass\* m_pBaseClass** Uygulamanız statik olarak MFC'ye bağlıysa, taban sınıfın yapısına `CRuntimeClass` işaretçi.

Bu işlev, sınıf uygulamasında [IMPLEMENT_DYNAMIC,](run-time-object-model-services.md#implement_dynamic) [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)veya [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) makrokullanımını gerektirir. Aksi takdirde yanlış sonuçlar alırsınız.

### <a name="example"></a>Örnek

Tüm `CAge` `CObject` örneklerde kullanılan sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCObjectSample#10](../../mfc/codesnippet/cpp/cobject-class_4.cpp)]

## <a name="cobjectiskindof"></a><a name="iskindof"></a>Cobject::Iskindof

Bu nesnenin belirli bir sınıfla ilişkisini sınar.

```
BOOL IsKindOf(const CRuntimeClass* pClass) const;
```

### <a name="parameters"></a>Parametreler

*pClass*<br/>
Türetilmiş sınıfınla ilişkili bir [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yapısına `CObject`işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Nesne sınıfa karşılık gelirse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, (1) belirtilen sınıfın bir nesnesi mi yoksa (2) belirtilen sınıftan türetilen bir sınıfın nesnesi olup olmadığını görmek için *pClass'ı* sınar. Bu işlev yalnızca [DECLARE_DYNAMIC,](run-time-object-model-services.md#declare_dynamic) [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate)veya [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) makroile bildirilen sınıflar için çalışır.

C++ çok biçimlilik özelliğini yendiği için bu işlevi kapsamlı olarak kullanmayın. Bunun yerine sanal işlevleri kullanın.

### <a name="example"></a>Örnek

Tüm `CAge` `CObject` örneklerde kullanılan sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCObjectSample#11](../../mfc/codesnippet/cpp/cobject-class_5.cpp)]

## <a name="cobjectisserializable"></a><a name="isserializable"></a>CObject::IsSerializable

Bu nesnenin serileştirme için uygun olup olmadığını sınama.

```
BOOL IsSerializable() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesne seri hale getirilebiliyorsa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir sınıfın serileştirilebilir olabilmesi için, bildiriminin [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) makroyu içermesi ve uygulamanın [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) makroyu içermesi gerekir.

> [!NOTE]
> Bu işlevi geçersiz kılmayın.

### <a name="example"></a>Örnek

Tüm `CAge` `CObject` örneklerde kullanılan sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCObjectSample#12](../../mfc/codesnippet/cpp/cobject-class_6.cpp)]

## <a name="cobjectoperator-delete"></a><a name="operator_delete"></a>CObject::operator silme

Kitaplığın Sürüm sürümü için, işleç **silme** işleci tarafından ayrılan belleği **yeni**.

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

Hata Ayıklama sürümünde, operatör **silme** bellek sızıntılarını algılamak için tasarlanmış bir ayırma izleme düzenine katılır.

Kod satırını kullanırsanız

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

herhangi bir uygulamadan önce bir . CPP dosyası, daha sonra **silmenin** üçüncü sürümü kullanılacak ve daha sonra raporlama için ayrılan blokta dosya adı ve satır numarası depolanır. Ekstra parametreleri sağlama konusunda endişelenmenize gerek yok; bir makro sizin için bu ilgilenir.

Hata Ayıklama modunda DEBUG_NEW kullanmasanız bile, yine de sızıntı algılaması elde edeyim, ancak yukarıda açıklanan kaynak dosya satırı numarası raporlaması olmadan.

**Yeni** işleçleri geçersiz kılar ve **silerseniz,** bu tanılama özelliğini kaybedersiniz.

### <a name="example"></a>Örnek

Bkz. [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) örneklerde `CAge` kullanılan sınıfın bir listesi için. `CObject`

[!code-cpp[NVC_MFCCObjectSample#15](../../mfc/codesnippet/cpp/cobject-class_8.cpp)]

## <a name="cobjectoperator-new"></a><a name="operator_new"></a>CObject::operatör yeni

Kitaplığın Sürüm sürümü için, **new** `malloc`işleç yeni benzer bir şekilde en iyi bellek ayırma gerçekleştirir.

```cpp
void* PASCAL operator new(size_t nSize);
void* PASCAL operator new(size_t, void* p);

void* PASCAL operator new(
    size_t nSize,
    LPCSTR lpszFileName,
    int nLine);
```

### <a name="remarks"></a>Açıklamalar

Hata Ayıklama sürümünde, operatör **yeni** bellek sızıntılarını algılamak için tasarlanmış bir ayırma izleme düzenine katılır.

Kod satırını kullanırsanız

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

herhangi bir uygulamadan önce bir . CPP dosyası, daha sonra **yeni** ikinci sürümü, daha sonra raporlama için ayrılan blokta dosya adı ve satır numarası depolama kullanılır. Ekstra parametreleri sağlama konusunda endişelenmenize gerek yok; bir makro sizin için bu ilgilenir.

Hata Ayıklama modunda DEBUG_NEW kullanmasanız bile, yine de sızıntı algılaması elde edeyim, ancak yukarıda açıklanan kaynak dosya satırı numarası raporlaması olmadan.

> [!NOTE]
> Bu işleci geçersiz kılarsanız, **silmeyi**de geçersiz kılmanız gerekir. Standart kitaplık `_new_handler` işlevini kullanmayın.

### <a name="example"></a>Örnek

Bkz. [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) örneklerde `CAge` kullanılan sınıfın bir listesi için. `CObject`

[!code-cpp[NVC_MFCCObjectSample#16](../../mfc/codesnippet/cpp/cobject-class_9.h)]

## <a name="cobjectserialize"></a><a name="serialize"></a>CObject::Serialize

Bu nesneyi arşivden veya arşivden okur veya yazar.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*<br/>
Seri `CArchive` hale getirmek için veya gelen bir nesne.

### <a name="remarks"></a>Açıklamalar

Seri hale `Serialize` getirmek istediğiniz her sınıf için geçersiz kılmanız gerekir. Geçersiz kılınan `Serialize` önce taban `Serialize` sınıfının işlevini çağırmalıdır.

Sınıf bildiriminizdeki [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) makroyu da kullanmanız ve uygulamada [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) makroyu kullanmanız gerekir.

[CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading) veya [CArchive kullanın::Arşivin](../../mfc/reference/carchive-class.md#isstoring) yüklenip yüklenmediğini veya depolanıp depolamadığını belirlemek için Storing.

`Serialize`CArchive tarafından [denir::ReadObject](../../mfc/reference/carchive-class.md#readobject) ve [CArchive::WriteObject](../../mfc/reference/carchive-class.md#writeobject). Bu işlevler ekleme `CArchive` işleci ( ** < **) ve ekstraksiyon işleci ( **>>** ile ilişkilidir).

Serileştirme örnekleri için [Serileştirme: Nesneyi Serileştirme](../../mfc/serialization-serializing-an-object.md)makalesine bakın.

### <a name="example"></a>Örnek

Tüm `CAge` `CObject` örneklerde kullanılan sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCObjectSample#13](../../mfc/codesnippet/cpp/cobject-class_10.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
