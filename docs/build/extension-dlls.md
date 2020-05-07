---
title: Uzantı DLL'leri
ms.date: 05/06/2019
helpviewer_keywords:
- memory [C++], DLLs
- MFC extension DLLs [C++]
- AFXDLL library
- shared resources [C++]
- MFC DLLs [C++], MFC extension DLLs
- DLLs [C++], extension
- shared DLL versions [C++]
- resource sharing [C++]
- extension DLLs [C++]
- extension DLLs [C++], about MFC extension DLLs
ms.assetid: f69ac3d4-e474-4b1c-87a1-6738843a135c
ms.openlocfilehash: 55b1e55a9c7bdf6daaff98a7fe3f1a2a55f68334
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220767"
---
# <a name="mfc-extension-dlls"></a>MFC uzantısı DLL’leri

MFC uzantı DLL 'si, genellikle varolan Microsoft Foundation Class Kitaplığı sınıflarından türetilen yeniden kullanılabilir sınıfları uygulayan bir DLL 'dir.

MFC uzantısı DLL 'SI aşağıdaki özelliklere ve gereksinimlere sahiptir:

- İstemci yürütülebilir dosyası, tanımlı ile `_AFXDLL` derlenen bir MFC uygulaması olmalıdır.

- MFC uzantı DLL 'SI, MFC 'ye dinamik olarak bağlanan normal bir MFC DLL tarafından da kullanılabilir.

- MFC uzantı dll 'Leri tanımlı ile `_AFXEXT` derlenmelidir. Bu da `_AFXDLL` tanımlanmaya zorlar ve uygun bildirimlerin MFC başlık dosyalarından çekilmesini sağlar. Ayrıca `AFX_EXT_CLASS` , MFC uzantı dll 'inizdeki `__declspec(dllexport)` sınıfları bildirmek üzere bu MAKROYU kullanıyorsanız gerekli olan DLL 'i oluştururken olarak tanımlanır.

- MFC uzantı dll 'Leri öğesinden `CWinApp`türetilmiş bir sınıf örneği oluşturmalıdır, ancak bu nesneyi sağlamak için istemci uygulamasını (veya dll) kullanmalıdır.

- Ancak MFC uzantı dll 'Leri, bir `DllMain` işlev sağlamalı ve gereken her türlü başlatmayı yapabilmelidir.

Uzantı dll 'Leri MFC 'nin dinamik bağlantı kitaplığı sürümü (MFC 'nin paylaşılan sürümü olarak da bilinir) kullanılarak oluşturulmuştur. MFC 'nin paylaşılan sürümüyle oluşturulmuş yalnızca MFC yürütülebilir dosyaları (uygulamalar veya normal MFC DLL 'Leri) MFC uzantısı DLL kullanabilir. Hem istemci uygulaması hem de MFC uzantısı DLL, MFCx0. dll ' nin aynı sürümünü kullanmalıdır. MFC uzantısı DLL 'SI ile MFC 'den yeni özel sınıflar türetebilir ve ardından bu genişletilmiş sürümü MFC 'nin DLL 'nizi çağıran uygulamalara sunabilirsiniz.

Uzantı dll 'Leri, uygulama ve DLL arasında MFC 'den türetilmiş nesneleri geçirmek için de kullanılabilir. Geçirilen nesneyle ilişkili üye işlevleri, nesnenin oluşturulduğu modülde bulunur. Bu işlevler, MFC 'nin paylaşılan DLL sürümü kullanılırken düzgün bir şekilde aktarıldığından, bir uygulama ile yüklenen MFC uzantı dll 'Leri arasında MFC veya MFC 'den türetilmiş nesne işaretçilerini serbestçe geçirebilirsiniz.

MFC uzantı DLL 'SI MFC 'nin paylaşılan bir sürümünü, bir uygulamanın, MFC 'nin paylaşılan DLL sürümünü kullanması için birkaç ek dikkat ile aynı şekilde kullanır:

- Türetilmiş bir `CWinApp`nesnesi yok. İstemci uygulamasının türetilmiş nesnesiyle birlikte `CWinApp`çalışmalıdır. Bu, istemci uygulamanın ana ileti göndericisi, boşta döngüsü vb. sahibi olduğu anlamına gelir.

- Kendi `DllMain` işlevinde `AfxInitExtensionModule` çağırır. Bu işlevin dönüş değeri denetlenmelidir. Öğesinden `AfxInitExtensionModule`sıfır değeri döndürülürse, işlevinizden `DllMain` 0 döndürün.

- MFC uzantısı DLL **CDynLinkLibrary** 'si uygulamaya nesneleri veya kaynakları dışarı aktarmak `CRuntimeClass` isterse, başlatma sırasında bir CDynLinkLibrary nesnesi oluşturur.

MFC 4,0 sürümünden önce, bu tür DLL bir AFXDLL olarak adlandırılmıştı. AFXDLL, DLL oluşturulurken `_AFXDLL` tanımlanan Önişlemci sembolünü ifade eder.

MFC 'nin paylaşılan sürümüne ait içeri aktarma kitaplıkları, [MFC DLL 'leri Için adlandırma kuralları](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions)bölümünde açıklanan kurala göre adlandırılır. Visual Studio, MFC DLL 'lerinin önceden oluşturulmuş sürümlerini ve uygulamalarınızda kullanabileceğiniz ve dağıtabileceğiniz MFC olmayan bir dizi dll 'Leri sağlar. Bunlar, Program Files\Microsoft Visual Studio klasörüne yüklenen Redist. txt dosyasında belgelenmiştir.

Bir. def dosyası kullanarak dışarı aktarıyorsanız, üst bilgi dosyanızın başına ve sonuna aşağıdaki kodu yerleştirin:

```cpp
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

Bu dört satır, kodunuzun bir MFC uzantısı DLL 'SI için doğru derlendiğinden emin olur. Bu dört satırı bırakmak DLL 'nizin yanlış derlenmesi ya da bağlantı oluşturmasına neden olabilir.

MFC DLL 'sine veya MFC DLL 'sinden bir MFC veya MFC 'den türetilmiş nesne işaretçisi geçirmeniz gerekiyorsa, DLL bir MFC uzantısı DLL olmalıdır. Geçirilen nesneyle ilişkili üye işlevleri, nesnenin oluşturulduğu modülde bulunur. Bu işlevler, MFC 'nin paylaşılan DLL sürümü kullanılırken düzgün bir şekilde aktarıldığından, bir uygulama ile yüklenen MFC uzantı dll 'Leri arasında MFC veya MFC 'den türetilmiş nesne işaretçilerini serbestçe geçirebilirsiniz.

C++ adı değiştirmeyi ve dışarı aktarma sorunları nedeniyle, bir MFC uzantısı DLL 'den dışarı aktarma listesi, farklı platformlar için aynı DLL ve DLL 'lerin hata ayıklama ve perakende sürümleri arasında farklı olabilir. Retail MFCx0. dll, 2.000 'e aktarılmış giriş noktası içerir; hata ayıklama MFCx0D. dll, 3.000 'e aktarılmış giriş noktaları içerir.

## <a name="memory-management"></a>Bellek Yönetimi

MFCx0. dll ve bir istemci uygulamasının adres alanına yüklenen tüm MFC uzantı dll 'Leri aynı uygulama için aynı bellek ayırıcı, kaynak yükleme ve diğer MFC genel durumlarını kullanın. Bu, MFC olmayan DLL kitaplıkları ve normal MFC DLL 'Leri tam tersini yaptığından ve her DLL 'in kendi bellek havuzunu ayırdığından, bu önemlidir.

Bir MFC uzantısı DLL 'SI bellek ayırırsa, bu bellek, uygulama tarafından ayrılan diğer herhangi bir nesneyle serbestçe dağıtılabilir. Ayrıca, MFC 'ye dinamik olarak bağlanan bir uygulama başarısız olursa, işletim sisteminin korunması DLL 'yi paylaşan diğer MFC uygulamalarının bütünlüğünü korur.

Benzer şekilde, kaynakları yüklemek için geçerli yürütülebilir dosya gibi diğer genel MFC durumları da istemci uygulaması ile tüm MFC uzantı dll 'Leri ve MFCx0. dll ' nin kendisi arasında da paylaşılır.

## <a name="sharing-resources-and-classes"></a>Kaynakları ve sınıfları paylaşma

Kaynakları dışa aktarma bir kaynak listesi aracılığıyla yapılır. Her uygulama, **CDynLinkLibrary** nesnelerinin listedir bağlantılı bir listesini içerir. Kaynak ararken, kaynakları yükleyen standart MFC uygulamalarının çoğu geçerli kaynak modülünde (`AfxGetResourceHandle`) önce görünür ve kaynak bulunamazsa, istenen kaynağı yüklemeye çalışan **CDynLinkLibrary** nesnelerinin listesini inceleyin.

Listenin yürümesi biraz daha yavaş olduğu ve kaynak KIMLIĞI aralıklarının yönetilmesi gereken dezavantajlara sahiptir. Birkaç MFC uzantı dll 'sine bağlantı sağlayan bir istemci uygulamasının, DLL örneği tanıtıcısını belirtmek zorunda kalmadan herhangi bir DLL tarafından sağlanmış kaynağı kullanabilmesi avantajına sahiptir. `AfxFindResourceHandle`, belirli bir eşleşmeyi aramak üzere kaynak listesini yürütirecek bir API 'dir. Bir kaynağın adını ve türünü alır ve ilk bulduğu kaynak tanıtıcısını (veya NULL) döndürür.

Listeye gitmek ve yalnızca belirli bir yerden kaynakları yüklemek istemiyorsanız, işlevleri `AfxGetResourceHandle` `AfxSetResourceHandle` kullanın ve eski tanıtıcıyı kaydedin ve yeni tanıtıcıyı ayarlayın. İstemci uygulamasına geri dönmek için eski kaynak tanıtıcısını geri yüklediğinizden emin olun. Bir menüyü açıkça yüklemek için bu yaklaşımı kullanmanın bir örneği için, bkz. TESTDLL2. cpp MFC örnek [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk).

MFC 'nin adı verilen MFC nesnelerinin dinamik olarak oluşturulması benzerdir. MFC nesne seri durumundan çıkarma mekanizmasının, daha önce depolanmaya `CRuntimeClass` dayalı olarak gerekli türde C++ nesnelerini dinamik olarak oluşturarak yeniden oluşturabilmesi için tüm nesneleri kayıtlı olması gerekir.

MFC örnek [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk)söz konusu olduğunda, liste şöyle görünür:

```
head ->   DLLHUSK.EXE   - or -   DLLHUSK.EXE
               |                      |
          TESTDLL2.DLL           TESTDLL2.DLL
               |                      |
          TESTDLL1.DLL           TESTDLL1.DLL
               |                      |
           MFCOxxD.DLL                |
               |                      |
           MFCDxxD.DLL                |
               |                      |
            MFCxxD.DLL            MFCxx.DLL
```

Burada *xx* sürüm numarasıdır; Örneğin 42, sürüm 4,2 ' yi temsil eder.

MFCxx. dll genellikle kaynak ve sınıf listesinde en son bir yoldur. MFCxx. dll tüm standart komut kimliklerinin istem dizeleri dahil olmak üzere tüm standart MFC kaynaklarını içerir. Listenin sonuna yerleştirilmesi dll 'Lerin ve istemci uygulamasının standart MFC kaynaklarının kendi kopyasına sahip olmasına izin verir, ancak bunun yerine MFCxx. dll içindeki paylaşılan kaynakları kullanır.

Tüm dll 'lerin kaynak ve sınıf adlarını istemci uygulamanın ad alanı içinde birleştirmek, seçtiğiniz kimlikleri veya adları dikkatli bir şekilde kullanmanızı gerektirmektir.

[DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk) örneği, birden çok üstbilgi dosyası kullanarak paylaşılan kaynak adı alanını yönetir.

MFC uzantı DLL 'nizin her uygulama için ek verileri tutması gerekiyorsa, **CDynLinkLibrary** 'den yeni bir sınıf türetebilir ve içinde `DllMain`oluşturabilirsiniz. Çalışırken, DLL, söz konusu MFC uzantısı DLL 'SI için bir tane bulmak üzere geçerli uygulamanın **CDynLinkLibrary** nesneleri listesini kontrol edebilir.

### <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [MFC uzantı DLL 'sini başlatma](run-time-library-behavior.md#initializing-extension-dlls)

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Paylaşılan kaynak dosyalarını kullanma hakkında ipuçları](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)

- [MFC 'nin DLL sürümü](../mfc/tn033-dll-version-of-mfc.md)

- [Statik olarak MFC'ye bağlı normal MFC DLL'leri](regular-dlls-statically-linked-to-mfc.md)

- [Dinamik olarak MFC'ye bağlı normal MFC DLL'leri](regular-dlls-dynamically-linked-to-mfc.md)

- [Normal MFC DLL 'Lerinde Database, OLE ve Sockets MFC uzantı dll 'Lerini kullanma](using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da C/C++ dll 'Leri oluşturma](dlls-in-visual-cpp.md)
