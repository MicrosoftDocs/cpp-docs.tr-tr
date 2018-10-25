---
title: CObject sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CObject [MFC], CObject
- CObject [MFC], AssertValid
- CObject [MFC], Dump
- CObject [MFC], GetRuntimeClass
- CObject [MFC], IsKindOf
- CObject [MFC], IsSerializable
- CObject [MFC], Serialize
ms.assetid: 95e9acd3-d9eb-4ac0-b52b-ca4a501a7a3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d16e3ca84b97aa1c6312ae9c634468b11ca86b9c
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50068188"
---
# <a name="cobject-class"></a>CObject sınıfı

Microsoft Foundation Class Kitaplığı için asıl taban sınıf.

## <a name="syntax"></a>Sözdizimi

```
class AFX_NOVTABLE CObject
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CObject::CObject](#cobject)|Varsayılan Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CObject::AssertValid](#assertvalid)|Bu nesnenin bütünlüğünü doğrular.|
|[CObject::Dump](#dump)|Bu nesne bir tanılama dökümü oluşturur.|
|[CObject::GetRuntimeClass](#getruntimeclass)|Döndürür `CRuntimeClass` bu nesnenin sınıfı için karşılık gelen yapısı.|
|[CObject::IsKindOf](#iskindof)|Bu nesnenin ilişki belirli bir sınıfa sınar.|
|[CObject::IsSerializable](#isserializable)|Bu nesne seri hale getirilebilir olup olmadığını görmek için sınar.|
|[CObject::Serialize](#serialize)|Yükler veya bir arşiv / için bir nesne depolar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CObject::operator Sil](#operator_delete)|Özel **Sil** işleci.|
|[Yeni CObject::operator](#operator_new)|Özel **yeni** işleci.|

## <a name="remarks"></a>Açıklamalar

Bu kitaplık sınıfları için yalnızca kök gibi görür `CFile` ve `CObList`, ancak aynı zamanda yazdığınız sınıflar için. `CObject` dahil olmak üzere temel hizmetleri sağlar

- Serileştirme desteği

- Çalışma zamanı sınıf bilgileri

- Nesne tanılama çıkışı

- Koleksiyon sınıfları ile uyumluluk

Unutmayın `CObject` birden çok devralmayı desteklemez. Türetilmiş sınıfları tek olabilir `CObject` temel sınıf ve `CObject` hiyerarşideki en soldaki olması gerekir. Ancak, yapıları için izin verilen olduğu ve olmayan- `CObject`-türetilmiş sınıflar sağ birden çok devralma dallarda.

Önemli avantajlar fark edeceksiniz `CObject` bazı isteğe bağlı makroları sınıfı uygulaması ve bildirimleri kullanırsanız türetme.

Birinci düzey makroları [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic) ve [ımplement_dynamıc](run-time-object-model-services.md#implement_dynamic), çalışma zamanı sınıf adını ve konumunu hiyerarşideki erişime. Bu, buna karşılık, anlamlı tanılama dökme sağlar.

İkinci düzey makroları [declare_serıal](run-time-object-model-services.md#declare_serial) ve [ımplement_serıal](run-time-object-model-services.md#implement_serial)birinci düzey makroları tüm işlevleri içerir ve "bir"Arşiv."gelen ve giden serileştirilmesi için" bir nesne tanırlar

Microsoft Foundation sınıfları ve C++ sınıfları genel türetme ve kullanma hakkında bilgi için `CObject`, bkz: [kullanarak CObject](../../mfc/using-cobject.md) ve [serileştirme](../../mfc/serialization-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CObject`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="assertvalid"></a>  CObject::AssertValid

Bu nesnenin bütünlüğünü doğrular.

```
virtual void AssertValid() const;
```

### <a name="remarks"></a>Açıklamalar

`AssertValid` İç durumunu denetleyerek bu nesne üzerinde bir geçerlilik denetimi gerçekleştirir. Kitaplığı hata ayıklama sürümünde `AssertValid` assert ve bu nedenle onaylama işlemi başarısız olduğu satır numarasını ve dosya adı listeleyen bir ileti ile programı sonlandırmak olabilir.

Kendi sınıfınızı yazdığınızda, geçersiz kılmalıdır `AssertValid` kendiniz ve sınıfının diğer kullanıcılar için tanı hizmetleri sağlamak için işlevi. Geçersiz kılınan `AssertValid` genellikle çağrıları `AssertValid` veri üyesi türetilmiş sınıf için benzersiz iade etmeden önce temel sınıfının işlevi.

Çünkü `AssertValid` olduğu bir **const** işlevi, test sırasında nesne durum değişikliği izin verilmez. Türetilmiş sınıfınızın `AssertValid` işlevleri özel durum oluşturması beklenmiyor ancak bunun yerine geçersiz nesne verileri algılamak onay.

"Geçerlilik" tanımını nesnenin sınıfa bağlıdır. Bir kural olarak, işlev "Basit denetleyin." gerçekleştirmelisiniz. Diğer bir deyişle, nesneyi diğer nesne işaretçileri içeriyorsa, işaretçi null olmayan, ancak işaretçiler tarafından başvurulan nesneler üzerinde test geçerlilik gerçekleştirmemelisiniz olup olmadığını görmek için denetlemelisiniz.

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm kullanılan sınıf `CObject` örnekler.

[!code-cpp[NVC_MFCCObjectSample#7](../../mfc/codesnippet/cpp/cobject-class_1.cpp)]

Başka bir örnek için bkz: [AfxDoForAllObjects](diagnostic-services.md#afxdoforallobjects).

##  <a name="cobject"></a>  CObject::CObject

Bu işlevler standarttır `CObject` oluşturucular.

```
CObject();
CObject(const CObject& objectSrc);
```

### <a name="parameters"></a>Parametreler

*objectSrc*<br/>
Başka bir başvuru `CObject`

### <a name="remarks"></a>Açıklamalar

Varsayılan sürüm, türetilmiş sınıf oluşturucu tarafından otomatik olarak çağrılır.

Sınıfınıza seri hale getirilebilir olması durumunda (ımplement_serıal makrosu içerir), sonra da, sınıf bildirimi içinde bir varsayılan Oluşturucusu (bağımsız değişken içermeyen bir oluşturucu) sahip olmalıdır. Varsayılan bir oluşturucu gerekmiyorsa, özel bir bildirmek veya "boş" Oluşturucu korumalı. Daha fazla bilgi için [kullanarak CObject](../../mfc/using-cobject.md).

Standart C++ varsayılan sınıf kopya oluşturucusuna bir üyesi tarafından üye kopyasını yapar. Özel durum `CObject` kopya Oluşturucu, sınıfın kopya Oluşturucu gerekiyor ancak yok ise, derleyici hata iletisinin garanti eder. Bu özellik sınıfınıza gerektiriyorsa, bu nedenle bir kopya Oluşturucu sağlamanız gerekir.

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` kullanılan sınıf `CObject` örnekler.

[!code-cpp[NVC_MFCCObjectSample#8](../../mfc/codesnippet/cpp/cobject-class_2.cpp)]

##  <a name="dump"></a>  CObject::Dump

Nesneniz için içeriğini dökümleri bir [CDumpContext](../../mfc/reference/cdumpcontext-class.md) nesne.

```
virtual void Dump(CDumpContext& dc) const;
```

### <a name="parameters"></a>Parametreler

*DC*<br/>
Genellikle, dökme için tanılama döküm bağlam `afxDump`.

### <a name="remarks"></a>Açıklamalar

Kendi sınıfınızı yazdığınızda, geçersiz kılmalıdır `Dump` kendiniz ve sınıfının diğer kullanıcılar için tanı hizmetleri sağlamak için işlevi. Geçersiz kılınan `Dump` genellikle çağrıları `Dump` veri üyesi türetilmiş sınıf için benzersiz yazdırmadan önce temel sınıfının işlevi. `CObject::Dump` sınıfınıza kullanıyorsa, sınıf adı yazdırır `IMPLEMENT_DYNAMIC` veya ımplement_serıal makrosu.

> [!NOTE]
>  `Dump` İşlevi, bir yeni satır karakteri çıktısını sonunda değil basmalıdır.

`Dump` çağrıları, yalnızca Microsoft Foundation Class Kitaplığı hata ayıklama sürümü mantıklı. Çağrıları, işlev bildirimleri ve işlev uygulamaları ile köşeli ayraç **#ifdef _DEBUG** /  `#endif` koşullu derleme deyimleri.

Bu yana `Dump` olduğu bir **const** işlevi, nesne durumu döküm sırasında değiştirmek izin verilmez.

[CDumpContext ekleme (<<) işleci](../../mfc/reference/cdumpcontext-class.md#operator_lt_lt) çağrıları `Dump` olduğunda bir `CObject` işaretçi eklenir.

`Dump` yalnızca "döngüsel olmayan yönlü" nesnelerin dökme izin verir. Örneğin, nesneleri listesi dökümü ancak nesnelerden biri listeyi ise, yığın taşması sonunda.

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm kullanılan sınıf `CObject` örnekler.

[!code-cpp[NVC_MFCCObjectSample#9](../../mfc/codesnippet/cpp/cobject-class_3.cpp)]

##  <a name="getruntimeclass"></a>  CObject::GetRuntimeClass

Döndürür `CRuntimeClass` bu nesnenin sınıfı için karşılık gelen yapısı.

```
virtual CRuntimeClass* GetRuntimeClass() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yapısı için bu nesnenin sınıfı; karşılık gelen hiçbir zaman **NULL**.

### <a name="remarks"></a>Açıklamalar

Bir `CRuntimeClass` her yapı `CObject`-türetilmiş sınıf. Yapı üyeleri aşağıdaki gibidir:

- **LPCSTR m_lpszClassName** ASCII sınıf adını içeren bir null ile sonlandırılmış dize.

- **int m_nObjectSize** nesnesinin bayt cinsinden boyutu. Nesne veri üyeleri o noktaya ayrılan bellek varsa, bu bellek boyutu dahil değil.

- **UINT m_wSchema** şema numarasını (-1 nonserializable sınıflar için). Bkz: [ımplement_serıal](run-time-object-model-services.md#implement_serial) makrosu şema numarasını açıklaması.

- **CObject\* (PASCAL\* m_pfnCreateObject) ()** sınıfınızın bir nesne oluşturur. varsayılan oluşturucu bir işlev işaretçisi (geçerli yalnızca dinamik oluşturma; sınıf destekliyorsa, aksi halde döndürür **NULL** ).

- **CRuntimeClass\* (PASCAL\* m_pfn_GetBaseClass) ()** uygulamanızı MFC AFXDLL sürümü dinamik olarak bağlı ise, döndüren bir işlev işaretçisine `CRuntimeClass` yapısı temel sınıf.

- **CRuntimeClass\* m_pBaseClass** MFC, işaretçi, uygulamanızın statik olarak bağlantılı olduğunu `CRuntimeClass` yapısı temel sınıf.

Bu işlev kullanılmasını gerektirir [ımplement_dynamıc](run-time-object-model-services.md#implement_dynamic), [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate), veya [ımplement_serıal](run-time-object-model-services.md#implement_serial) sınıfı uygulamasında makrosu. Aksi takdirde yanlış sonuçlar alırsınız.

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm kullanılan sınıf `CObject` örnekler.

[!code-cpp[NVC_MFCCObjectSample#10](../../mfc/codesnippet/cpp/cobject-class_4.cpp)]

##  <a name="iskindof"></a>  CObject::IsKindOf

Bu nesnenin ilişki belirli bir sınıfa sınar.

```
BOOL IsKindOf(const CRuntimeClass* pClass) const;
```

### <a name="parameters"></a>Parametreler

*pClass*<br/>
Bir işaretçi bir [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) ilişkili yapısı, `CObject`-türetilmiş sınıf.

### <a name="return-value"></a>Dönüş Değeri

Nesne sınıfı için karşılık gelen olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlevi test *pClass* (1) belirtilen sınıfın bir nesnesi veya (2), belirtilen sınıftan türetilmiş bir sınıfın bir nesnesi, görmek için. Bu işlev yalnızca sınıfları ile bildirilen çalışır [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic), [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate), veya [declare_serıal](run-time-object-model-services.md#declare_serial) makrosu.

C++ çok biçimlilik özellik programlamasıdır olduğundan, bu işlev kapsamlı olarak kullanmayın. Sanal işlevler kullanın.

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm kullanılan sınıf `CObject` örnekler.

[!code-cpp[NVC_MFCCObjectSample#11](../../mfc/codesnippet/cpp/cobject-class_5.cpp)]

##  <a name="isserializable"></a>  CObject::IsSerializable

Bu nesne seri hale getirme için uygun olup olmadığını sınar.

```
BOOL IsSerializable() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesne seri hale getirilebilir olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Seri hale getirilebilir bir sınıf için bildiriminden içermelidir [declare_serıal](run-time-object-model-services.md#declare_serial) makrosu ve uygulama içermelidir [ımplement_serıal](run-time-object-model-services.md#implement_serial) makrosu.

> [!NOTE]
>  Bu işlev geçersiz kılmaz.

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm kullanılan sınıf `CObject` örnekler.

[!code-cpp[NVC_MFCCObjectSample#12](../../mfc/codesnippet/cpp/cobject-class_6.cpp)]

##  <a name="operator_delete"></a>  CObject::operator Sil

Kitaplık sürümü için işleci **Sil** işleci tarafından ayrılan bellek serbest bırakma **yeni**.

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

Hata ayıklama sürümünde işleci **Sil** bellek sızıntılarını algılamak için tasarlanmış bir ayırma izleme düzeninde katılır.

Kod satırı kullanıyorsanız

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

Tüm uygulamalarınızda önce bir. CPP dosyasına, ardından üçüncü sürümünü **Sil** dosya adı ve satır numarasını daha sonra raporlama için ayrılmış bir blok depolama kullanılır. Ek parametreler sağlayarak hakkında endişelenmeniz gerekmez; Makro, sizin için üstlenir.

Hata ayıklama modunda DEBUG_NEW kullanmayın bile almaya devam ediyorsanız, sızıntı algılaması ancak yukarıda açıklanan satır numarası kaynak dosyası raporlama olmadan.

İşleçler geçersiz kılarsanız **yeni** ve **Sil**, bu tanılama özelliği kaybeder.

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` kullanılan sınıf `CObject` örnekler.

[!code-cpp[NVC_MFCCObjectSample#15](../../mfc/codesnippet/cpp/cobject-class_8.cpp)]

##  <a name="operator_new"></a>  Yeni CObject::operator

Kitaplık sürümü için işleci **yeni** en iyi bellek ayırma için benzer bir şekilde gerçekleştirir `malloc`.

```
void* PASCAL operator new(size_t nSize);
void* PASCAL operator new(size_t, void* p);

void* PASCAL operator new(
    size_t nSize,
    LPCSTR lpszFileName,
    int nLine);
```

### <a name="remarks"></a>Açıklamalar

Hata ayıklama sürümünde işleci **yeni** bellek sızıntılarını algılamak için tasarlanmış bir ayırma izleme düzeninde katılır.

Kod satırı kullanıyorsanız

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

Tüm uygulamalarınızda önce bir. CPP dosyasına, ardından ikinci sürümü **yeni** dosya adı ve satır numarasını daha sonra raporlama için ayrılmış bir blok depolama kullanılır. Ek parametreler sağlayarak hakkında endişelenmeniz gerekmez; Makro, sizin için üstlenir.

Hata ayıklama modunda DEBUG_NEW kullanmayın bile almaya devam ediyorsanız, sızıntı algılaması ancak yukarıda açıklanan satır numarası kaynak dosyası raporlama olmadan.

> [!NOTE]
>  Bu işleç geçersiz kılarsanız, geçersiz kılmalısınız **Sil**. Standart kitaplık kullanmayın `_new_handler` işlevi.

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` kullanılan sınıf `CObject` örnekler.

[!code-cpp[NVC_MFCCObjectSample#16](../../mfc/codesnippet/cpp/cobject-class_9.h)]

##  <a name="serialize"></a>  CObject::Serialize

Okur veya ya da bir arşivden bu nesneyi yazar.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*ar*<br/>
A `CArchive` gelen veya giden serileştirmek için nesne.

### <a name="remarks"></a>Açıklamalar

Geçersiz kılmanız gerekir `Serialize` seri hale getirmek istediğiniz her sınıf için. Geçersiz kılınan `Serialize` çağırmalısınız `Serialize` işlevi, kendi temel sınıfı.

Ayrıca kullanmalısınız [declare_serıal](run-time-object-model-services.md#declare_serial) makrosu, sınıf bildirimi ve kullanması gerekir [ımplement_serıal](run-time-object-model-services.md#implement_serial) uygulamasında makrosu.

Kullanım [CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading) veya [CArchive::IsStoring](../../mfc/reference/carchive-class.md#isstoring) Arşiv yüklenirken depolama olup olmadığını belirlemek için.

`Serialize` çağıran [CArchive::ReadObject](../../mfc/reference/carchive-class.md#readobject) ve [CArchive::WriteObject](../../mfc/reference/carchive-class.md#writeobject). Bu işlevler ile ilişkili `CArchive` ekleme operatörü ( **< \<**) ve çıkarma işleci ( **>>**).

Serileştirme örnekler için bkz [seri hale getirme: bir nesneyi serileştirmek](../../mfc/serialization-serializing-an-object.md).

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm kullanılan sınıf `CObject` örnekler.

[!code-cpp[NVC_MFCCObjectSample#13](../../mfc/codesnippet/cpp/cobject-class_10.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

