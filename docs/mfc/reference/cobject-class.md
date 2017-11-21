---
title: "CObject sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
helpviewer_keywords:
- CObject [MFC], CObject
- CObject [MFC], AssertValid
- CObject [MFC], Dump
- CObject [MFC], GetRuntimeClass
- CObject [MFC], IsKindOf
- CObject [MFC], IsSerializable
- CObject [MFC], Serialize
ms.assetid: 95e9acd3-d9eb-4ac0-b52b-ca4a501a7a3a
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 170a6db8bfbba83722f9649c52d7a7e3d65761ba
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
|[CObject::CObject](#cobject)|Varsayılan Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CObject::AssertValid](#assertvalid)|Bu nesnenin bütünlüğünü doğrular.|  
|[CObject::Dump](#dump)|Bu nesne, bir tanı dökümü üretir.|  
|[CObject::GetRuntimeClass](#getruntimeclass)|Döndürür `CRuntimeClass` bu nesnenin sınıfına karşılık gelen yapısı.|  
|[CObject::IsKindOf](#iskindof)|Belirli bir sınıfın bu nesnenin ilişki sınar.|  
|[CObject::IsSerializable](#isserializable)|Bu nesne seri hale görmek için sınar.|  
|[CObject::Serialize](#serialize)|Yükler veya bir arşiv başlangıç/bitiş bir nesne depolar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CObject::operator Sil](#operator_delete)|Özel **silmek** işleci.|  
|[Yeni CObject::operator](#operator_new)|Özel **yeni** işleci.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu kitaplık sınıfları için yalnızca kök gibi görevi gören `CFile` ve `CObList`, ancak aynı zamanda yazdığınız sınıfları için. `CObject`dahil olmak üzere temel hizmetleri sağlar  
  
-   Serileştirme desteği  
  
-   Çalışma zamanı sınıf bilgileri  
  
-   Nesne tanılama çıktıları  
  
-   Koleksiyon sınıfları ile uyumluluk  
  
 Unutmayın `CObject` birden çok devralma desteklemiyor. Türetilen sınıflar yalnızca bir bulunabilir `CObject` temel sınıf ve `CObject` hiyerarşideki en soldaki olması gerekir. Ancak, yapıları için izin verilen, olmasından ve olmayan- `CObject`-sağ taraftaki birden çok devralmayı dalları sınıflarda türetilmiş.  
  
 Gelen önemli faydası fark `CObject` isteğe bağlı makroları sınıf uygulamasını ve bildirimlerin bazıları kullanırsanız türetme.  
  
 Birinci düzey makroları [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic) ve [ımplement_dynamıc](run-time-object-model-services.md#implement_dynamic), çalışma zamanı sınıf adını ve konumunu hiyerarşideki erişime. Bu, sırasıyla anlamlı tanılama dökme sağlar.  
  
 İkinci düzey makroları [declare_serıal](run-time-object-model-services.md#declare_serial) ve [ımplement_serıal](run-time-object-model-services.md#implement_serial), birinci düzey makroları tüm işlevselliğini içerir ve "için ve bir"Arşiv."serileştirilmesi için" bir nesne etkinleştir  
  
 Microsoft Foundation sınıfları ve C++ sınıfları genel türetme ve kullanma hakkında bilgi için `CObject`, bkz: [kullanarak CObject](../../mfc/using-cobject.md) ve [seri hale getirme](../../mfc/serialization-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CObject`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
  
##  <a name="assertvalid"></a>CObject::AssertValid  
 Bu nesnenin bütünlüğünü doğrular.  
  
```  
virtual void AssertValid() const;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `AssertValid`Bu nesne üzerinde bir geçerlilik denetimi iç durumunu denetleyerek gerçekleştirir. Kitaplığı, hata ayıklama sürümünde `AssertValid` assert ve böylece onaylama başarısız olduğu satır numarasını ve dosya adını listeleyen bir ileti ile programı sonlandırmak olabilir.  
  
 Kendi sınıfı yazdığınızda, geçersiz kılmalısınız `AssertValid` kendiniz ve diğer kullanıcıların sınıfınızın için tanı hizmetleri sağlayan işlev. Geçersiz kılınan `AssertValid` genellikle çağırır `AssertValid` veri üyeleri türetilmiş sınıf benzersiz etmeden olduğu temel sınıfın işlevi.  
  
 Çünkü `AssertValid` olan bir **const** işlevi, test sırasında nesne durum değişikliği izin verilmez. Kendi türetilmiş bir sınıf `AssertValid` işlevleri özel durumlar oluşturmamalıdır ancak bunun yerine geçersiz nesne verileri algılamak assert.  
  
 "Geçerlilik" tanımını nesne sınıfında bağlıdır. Bir kural olarak, işlev "Basit onay." gerçekleştirmeniz gerekir Diğer bir deyişle, bir nesne diğer nesnelerine işaretçiler içeriyorsa, işaretçileri null değildir, ancak işaretçiler tarafından başvurulan nesne üzerinde test geçerlilik gerçekleştirmesi gereken değil olup olmadığını görmek için kontrol etmeniz gerekir.  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tümünde kullanılan sınıf `CObject` örnekler.  
  
 [!code-cpp[NVC_MFCCObjectSample#7](../../mfc/codesnippet/cpp/cobject-class_1.cpp)]  
  
 Başka bir örnek için bkz: [AfxDoForAllObjects](diagnostic-services.md#afxdoforallobjects).  
  
##  <a name="cobject"></a>CObject::CObject  
 Bu işlevler standarttır `CObject` oluşturucular.  
  
```  
CObject();  
CObject(const CObject& objectSrc);
```  
  
### <a name="parameters"></a>Parametreler  
 *objectSrc*  
 Başka bir başvuru`CObject`  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan sürüm, türetilmiş sınıf oluşturucu tarafından otomatik olarak çağrılır.  
  
 Sınıfınıza seri hale getirilebilir ise (bunu içerir `IMPLEMENT_SERIAL` makrosu), sonra da sınıfı bildiriminde bir varsayılan Oluşturucusu (bağımsız değişken içermeyen bir oluşturucuya) olması gerekir. Varsayılan bir oluşturucu gerekmiyorsa, özel bildirme veya "boş" Oluşturucusu korumalı. Daha fazla bilgi için bkz: [kullanarak CObject](../../mfc/using-cobject.md).  
  
 Standart C++ varsayılan sınıf kopya Oluşturucu bir üyesi tarafından üye kopya yapar. Özel durum `CObject` kopya Oluşturucu sınıfınızın kopya Oluşturucu gerekiyor ancak yok ise derleyici hata iletisi garanti eder. Bu özellik sınıfınız gerektiriyorsa, bu nedenle kopya Oluşturucu sağlamanız gerekir.  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` kullanılan sınıf `CObject` örnekler.  
  
 [!code-cpp[NVC_MFCCObjectSample#8](../../mfc/codesnippet/cpp/cobject-class_2.cpp)]  
  
##  <a name="dump"></a>CObject::Dump  
 Nesnenin içeriğini dökümleri bir [CDumpContext](../../mfc/reference/cdumpcontext-class.md) nesnesi.  
  
```  
virtual void Dump(CDumpContext& dc) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `dc`  
 Döküm alma, genellikle için tanılama döküm bağlamı `afxDump`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kendi sınıfı yazdığınızda, geçersiz kılmalısınız `Dump` kendiniz ve diğer kullanıcıların sınıfınızın için tanı hizmetleri sağlayan işlev. Geçersiz kılınan `Dump` genellikle çağırır `Dump` veri üyeleri türetilmiş sınıf benzersiz yazdırma önce kendi temel sınıfının işlevi. `CObject::Dump`sınıfınızda kullanıyorsa, sınıf adını yazdırır `IMPLEMENT_DYNAMIC` veya `IMPLEMENT_SERIAL` makrosu.  
  
> [!NOTE]
>  `Dump` İşlevi çıktısını sonunda yeni satır karakteri yazdırma.  
  
 `Dump`aramaları yalnızca Microsoft Foundation Class Kitaplığı hata ayıklama sürümü anlamlıdır. Çağrılar, işlev bildirimleri ve işlev uygulamaları ile köşeli ayraç **#ifdef _DEBUG** /  `#endif` deyimleri koşullu derleme için.  
  
 Bu yana `Dump` olan bir **const** işlevi, nesne durumu döküm sırasında değiştirmek izin verilmez.  
  
 [CDumpContext ekleme (<<) işleci](../../mfc/reference/cdumpcontext-class.md#operator_lt_lt) çağrıları `Dump` zaman bir `CObject` işaretçi eklenir.  
  
 `Dump`"Çevrimsiz" yalnızca nesnelerin dökme izin verir. Örneğin, bir nesne, listesi dökümü ancak nesnelerden listesi ise, yığın taşması sonunda.  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tümünde kullanılan sınıf `CObject` örnekler.  
  
 [!code-cpp[NVC_MFCCObjectSample#9](../../mfc/codesnippet/cpp/cobject-class_3.cpp)]  
  
##  <a name="getruntimeclass"></a>CObject::GetRuntimeClass  
 Döndürür `CRuntimeClass` bu nesnenin sınıfına karşılık gelen yapısı.  
  
```  
virtual CRuntimeClass* GetRuntimeClass() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yapısı bu nesnenin sınıfına; karşılık gelen hiçbir zaman **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir `CRuntimeClass` yapısı her `CObject`-türetilmiş sınıf. Yapı üyeleri aşağıdaki gibidir:  
  
- **LPCSTR m_lpszClassName** null ile sonlandırılmış ASCII sınıf adını içeren bir dize.  
  
- **int m_nObjectSize** nesnesinin bayt cinsinden boyutu. Nesne ayrılmış bellek o noktaya veri üyeleri varsa, bu bellek boyutu dahil değil.  
  
- **UINT m_wSchema** şema numarasını (-1 nonserializable sınıfları için). Bkz: [ımplement_serıal](run-time-object-model-services.md#implement_serial) makrosu şema numarasını açıklaması.  
  
- **CObject\* (PASCAL\* m_pfnCreateObject) ()** , sınıfın bir nesnesi oluşturur varsayılan oluşturucu için bir işlev işaretçisi (geçerli yalnızca dinamik oluşturma; sınıfı destekliyorsa, aksi takdirde, döndürür **NULL** ).  
  
- **CRuntimeClass\* (PASCAL\* m_pfn_GetBaseClass) ()** uygulamanızı MFC AFXDLL sürümü dinamik olarak bağlı ise, bir işlev işaretçisi döndüren `CRuntimeClass` yapısı temel sınıf.  
  
- **CRuntimeClass\* m_pBaseClass** MFC, bir işaretçi uygulamanızı statik olarak bağlantılı olduğunu `CRuntimeClass` yapısı temel sınıf.  
  
 Bu işlev kullanılmasını gerektiren [ımplement_dynamıc](run-time-object-model-services.md#implement_dynamic), [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate), veya [ımplement_serıal](run-time-object-model-services.md#implement_serial) makrosu sınıfı uygulamasında. Aksi takdirde yanlış sonuçları alırsınız.  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tümünde kullanılan sınıf `CObject` örnekler.  
  
 [!code-cpp[NVC_MFCCObjectSample#10](../../mfc/codesnippet/cpp/cobject-class_4.cpp)]  
  
##  <a name="iskindof"></a>CObject::IsKindOf  
 Belirli bir sınıfın bu nesnenin ilişki sınar.  
  
```  
BOOL IsKindOf(const CRuntimeClass* pClass) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pClass`  
 Bir işaretçi bir [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) ilişkili yapısı, `CObject`-türetilmiş sınıf.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesne için sınıf karşılık geliyorsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev testleri `pClass` (1), belirtilen sınıfın bir nesnesi olması veya (2), belirtilen sınıfından türetilen bir sınıftan bir nesneyi görmek için. Bu işlev yalnızca ile bildirilen sınıfları için çalışır [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic), [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate), veya [declare_serıal](run-time-object-model-services.md#declare_serial) makrosu.  
  
 C++ çok biçimlilik özelliği defeats olmadığından bu işlev yaygın kullanmayın. Sanal işlevler kullanın.  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tümünde kullanılan sınıf `CObject` örnekler.  
  
 [!code-cpp[NVC_MFCCObjectSample#11](../../mfc/codesnippet/cpp/cobject-class_5.cpp)]  
  
##  <a name="isserializable"></a>CObject::IsSerializable  
 Bu nesne seri hale getirme için uygun olup olmadığını sınar.  
  
```  
BOOL IsSerializable() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu, sıfır olmayan bir nesne seri hale getirilebilir; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Seri hale getirilebilir bir sınıf için bildiriminden içermelidir [declare_serıal](run-time-object-model-services.md#declare_serial) makrosu ve uygulama içermelidir [ımplement_serıal](run-time-object-model-services.md#implement_serial) makrosu.  
  
> [!NOTE]
>  Bu işlev geçersiz kılmaz.  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tümünde kullanılan sınıf `CObject` örnekler.  
  
 [!code-cpp[NVC_MFCCObjectSample#12](../../mfc/codesnippet/cpp/cobject-class_6.cpp)]  
  
##  <a name="operator_delete"></a>CObject::operator Sil  
 Kitaplığı sürümü için işleci **silmek** operatör tarafından ayrılan bellek boşaltır **yeni**.  
  
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
 Hata ayıklama sürümünde işleci **silmek** bellek sızıntıları algılamak üzere tasarlanmış bir ayırma izleme düzeninde katılır.  
  
 Kod satırı kullanıyorsanız  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]  
  
 Uygulamalarınızda hiçbirini önce bir. CPP dosya, ardından üçüncü sürümü **silmek** filename ve satır numarası daha sonra raporlama için ayrılmış blok depolamak kullanılır. Ek parametreler sağlama hakkında endişelenmeniz gerekmez; Makro alır, sizin için gerçekleştirir.  
  
 Kullanmaz olsa bile `DEBUG_NEW` hata ayıklama modunda hala sızıntısı algılama, aldığınız ancak kaynak dosya satır numarası raporlama yukarıda açıklanan olmadan.  
  
 İşleçler geçersiz kılarsanız **yeni** ve **silmek**, bu tanılama özelliği kaybeder.  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` kullanılan sınıf `CObject` örnekler.  
  
 [!code-cpp[NVC_MFCCObjectSample#15](../../mfc/codesnippet/cpp/cobject-class_8.cpp)]  
  
##  <a name="operator_new"></a>Yeni CObject::operator  
 Kitaplığı sürümü için işleci **yeni** benzer bir şekilde en iyi bellek ayırma gerçekleştirir `malloc`.  
  
```  
void* PASCAL operator new(size_t nSize);  
void* PASCAL operator new(size_t, void* p);

 
void* PASCAL operator new(
    size_t nSize,  
    LPCSTR lpszFileName,  
    int nLine);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Hata ayıklama sürümünde işleci **yeni** bellek sızıntıları algılamak üzere tasarlanmış bir ayırma izleme düzeninde katılır.  
  
 Kod satırı kullanıyorsanız  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]  
  
 Uygulamalarınızda hiçbirini önce bir. CPP dosya, ardından ikinci sürümü **yeni** filename ve satır numarası daha sonra raporlama için ayrılmış blok depolamak kullanılır. Ek parametreler sağlama hakkında endişelenmeniz gerekmez; Makro alır, sizin için gerçekleştirir.  
  
 Kullanmaz olsa bile `DEBUG_NEW` hata ayıklama modunda hala sızıntısı algılama, aldığınız ancak kaynak dosya satır numarası raporlama yukarıda açıklanan olmadan.  
  
> [!NOTE]
>  Bu işleç geçersiz kılarsanız geçersiz kılmalısınız **silmek**. Standart Kitaplığı kullanmayın **_new_handler** işlevi.  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` kullanılan sınıf `CObject` örnekler.  
  
 [!code-cpp[NVC_MFCCObjectSample#16](../../mfc/codesnippet/cpp/cobject-class_9.h)]  
  
##  <a name="serialize"></a>CObject::Serialize  
 Okur veya bir arşiv değiştirilmesine veya bu nesneyi yazar.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parametreler  
 `ar`  
 A `CArchive` gelen veya giden serileştirmek için nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçersiz kılmanız gerekir `Serialize` seri hale getirmek istediğiniz her sınıf için. Geçersiz kılınan `Serialize` ilk çağırmalısınız `Serialize` olduğu temel sınıfın işlevi.  
  
 Ayrıca kullanmanız gerekir [declare_serıal](run-time-object-model-services.md#declare_serial) makrosu sınıf bildirimi ve kullanmalıdır [ımplement_serıal](run-time-object-model-services.md#implement_serial) uygulamasında makrosu.  
  
 Kullanım [CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading) veya [CArchive::IsStoring](../../mfc/reference/carchive-class.md#isstoring) Arşiv yüklenirken veya depolama olup olmadığını belirlemek için.  
  
 `Serialize`tarafından çağrılır [CArchive::ReadObject](../../mfc/reference/carchive-class.md#readobject) ve [CArchive::WriteObject](../../mfc/reference/carchive-class.md#writeobject). Bu işlevler ilişkili `CArchive` ekleme işleci (  **< \<** ) ve ayıklama işleci (  **>>** ).  
  
 Serileştirme örnekler için bkz: [seri hale getirme: bir nesneyi seri hale getirme](../../mfc/serialization-serializing-an-object.md).  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tümünde kullanılan sınıf `CObject` örnekler.  
  
 [!code-cpp[NVC_MFCCObjectSample#13](../../mfc/codesnippet/cpp/cobject-class_10.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)



