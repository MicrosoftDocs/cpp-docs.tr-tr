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
# <a name="mfc-extension-dlls"></a>MFC uzantı DLL'leri

Bir MFC uzantılı DLL genellikle varolan Microsoft Foundation Class Kitaplığı sınıflarından türetilen yeniden kullanılabilir sınıfları uygulayan bir DLL'dir.

Bir MFC uzantılı DLL aşağıdaki özellikleri ve gereksinimleri vardır:

- İstemci yürütülebilir bir MFC uygulaması ile derlenmiş olmalıdır `_AFXDLL` tanımlı.

- Bir MFC uzantılı DLL, dinamik olarak MFC'ye bağlı normal MFC DLL'SİNİN tarafından da kullanılabilir.

- MFC uzantı DLL'leri ile derlenmelidir `_AFXEXT` tanımlı. Bu zorlar `_AFXDLL` de tanımlanmasını ve uygun bildirimlerin çekilmesini MFC üst bilgi dosyaları sağlar. Ayrıca, sağlar `AFX_EXT_CLASS` olarak tanımlanan `__declspec(dllexport)` DLL'si oluşturulurken olduğu sınıflar, MFC uzantısı DLL bildirmek için bu makroyu kullanıyorsanız gerekli.

- MFC uzantı DLL'leri, türetilen bir sınıf oluşturmamalı `CWinApp`, ancak istemci uygulaması (veya DLL) Bu nesne için yararlanmalıdır.

- MFC uzantı DLL'leri ancak sağlaması bir `DllMain` işlev ve gerekli sıfırlamaları yok yapın.

Uzantı DLL'leri MFC (diğer adıyla MFC paylaşılan sürüm) dinamik bağlantı kitaplığı sürümü kullanılarak oluşturuldu. Bir MFC uzantılı DLL, MFC paylaşılan sürümü ile oluşturulmuş yalnızca MFC yürütülebilir dosyaları (uygulama veya Normal MFC DLL'leri) kullanabilirsiniz. Hem istemci uygulaması hem de MFC uzantısı DLL MFCx0.dll aynı sürümünü kullanmanız gerekir. Bir MFC uzantılı DLL ile yeni özel sınıflar türetebilir ve ardından MFC genişletilmiş bu sürümü DLL'nizi çağıran uygulamalara sunar.

Uzantı DLL'leri, uygulama ve DLL arasında MFC'den türetilmiş nesneler geçirmek için de kullanılabilir. Geçirilen nesneyle ilişkili üye işlevleri, nesne oluşturulduğu modülünde mevcut. Bu işlevler düzgün bir şekilde paylaşılan MFC DLL sürümünü kullanırken dışarı aktarıldığı için MFC serbestçe geçirebilir veya uygulama ile MFC uzantısı DLL'leri arasında MFC'den türetilmiş nesne işaretçileri.

Bir MFC uzantılı DLL MFC paylaşılan bir sürümü ile bazı ek hususlar MFC, paylaşılan DLL sürümü bir uygulamanın kullandığı aynı şekilde kullanır:

- Sahip olmadığı bir `CWinApp`-türetilmiş bir nesneye. Birlikte çalışmalıdır `CWinApp`-türetilmiş bir nesneye istemci uygulaması. Bu, istemci uygulama ana ileti pompası, boşta döngü ve benzeri sahibi olduğu anlamına gelir.

- Çağrı `AfxInitExtensionModule` içinde kendi `DllMain` işlevi. Bu işlevin dönüş değeri denetlenmelidir. Sıfır değerini döndürdüyse `AfxInitExtensionModule`, 0'dan iade, `DllMain` işlevi.

- Oluşturur bir **CDynLinkLibrary** MFC uzantısı DLL dışarı aktarma istediğinde, başlatma sırasında nesne `CRuntimeClass` nesneleri veya kaynakları uygulama.

MFC 4.0 sürümünden önce bu tür bir DLL AFXDLL çağrıldı. AFXDLL başvurduğu `_AFXDLL` DLL'si oluşturulurken tanımlanan önişlemci sembolü.

İçeri aktarma kitaplıkları için MFC'nin paylaşılan sürümünden açıklanan kurallara göre adlandırılır [MFC DLL'leri için adlandırma kuralları](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions). Visual Studio MFC DLL'lerinin yanı sıra, MFC olmayan kullanan ve uygulamalarınızı dağıtmak DLL'leri birkaç önceden oluşturulmuş sürümleri sağlar. Bu Program Files\Microsoft Visual Studio klasöre yüklenen REDIST.txt belgelenmiştir.

Bir .def dosyası kullanarak dışa aktarıyorsanız aşağıdaki kodu, üst bilgi dosyası başında ve sonunda yerleştirin:

```cpp
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

Bu dört satırı, kodunuzu bir MFC uzantılı DLL için doğru derlendiğinden emin olun. Bu dört satırı dışarıda bırakarak, derleme veya yanlış bir DLL dosyanız neden olabilir.

MFC'den türetilmiş nesne işaretçisi için ya da MFC DLL, DLL Dosyasının bir MFC uzantılı DLL olmalıdır veya MFC geçirmek ihtiyacınız olur. Geçirilen nesneyle ilişkili üye işlevleri, nesne oluşturulduğu modülünde mevcut. Bu işlevler düzgün bir şekilde paylaşılan MFC DLL sürümünü kullanırken dışarı aktarıldığı için MFC serbestçe geçirebilir veya uygulama ile MFC uzantısı DLL'leri arasında MFC'den türetilmiş nesne işaretçileri.

C++ ad değiştirmeyi ve dışarı aktarma sorunları nedeniyle, dışarı aktarma listeden bir MFC uzantılı DLL farklı platformlar için aynı DLL'nin hata ayıklama ve perakende sürümleri ve DLL'ler farklı olabilir. Perakende MFCx0.dll yaklaşık 2.000 giriş noktaları dışarı; ' % s'hata MFCx0D.dll yaklaşık 3000 dışarı aktarılan giriş noktaları vardır.

## <a name="memory-management"></a>Bellek Yönetimi

Aynı uygulamada değilmiş gibi MFCx0.dll ve tüm MFC uzantısı DLL'leri bir istemci uygulamanın adres alanına yüklenen aynı bellek ayırıcısı, kaynak yükleme ve diğer MFC genel durumlarını kullanın. MFC olmayan DLL kitaplıkları ve Normal MFC DLL'leri tam tersi yapın ve her DLL, kendi bellek havuzunda yetersiz ayırma sahip olduğundan bu önemlidir.

Bir MFC uzantılı DLL bellek ayırırsa, bellek diğer uygulama ayrılan nesneleri serbestçe intermix. Ayrıca, dinamik olarak MFC'ye bağlanan bir uygulama başarısız olursa, işletim sisteminin koruma DLL paylaşımı başka bir MFC Uygulama bütünlüğünü korur.

Benzer şekilde, kaynakları yüklemek için geçerli yürütülebilir dosya gibi diğer genel MFC durumları da istemci uygulaması ve tüm MFC uzantısı DLL'leri yanı sıra arasında MFCx0.dll kendisini paylaşılır.

## <a name="sharing-resources-and-classes"></a>Kaynakları ve sınıfları paylaşma

Kaynakları dışarı aktarma, bir kaynak listesi üzerinden gerçekleştirilir. Her uygulamanın tek bağlı listesini içeren **CDynLinkLibrary** nesneleri. Bir kaynak ararken kaynakları yükleme standart MFC uygulamalarının çoğunu geçerli kaynak modülüne bakın (`AfxGetResourceHandle`) ve kaynak bulunmazsa yol listesi **CDynLinkLibrary** nesneleri İstenen kaynak yüklenmeye çalışılıyor.

Listenin anlatarak biraz daha yavaş olması ve kaynak kimliği aralıklarını yönetmeyi gerektirir dezavantajları vardır. Bu, birkaç MFC uzantısı DLL'leri bağlanan istemci uygulaması herhangi bir DLL tarafından sağlanan kaynak DLL örneğinin tutamacını belirtmenize gerek kalmadan kullanabilirsiniz avantajına sahiptir. `AfxFindResourceHandle` bir API için belirli bir eşleşme aramak için kaynak listesinden walking için kullanılır. Bir kaynak türünü ve adını alır ve ilk bulunduğu kaynak tutamacının (veya NULL) döndürür.

Listeyi izlemek ve yalnızca belirli bir konumdan kaynakları yüklemek istemiyorsanız, İşlevler kullanın `AfxGetResourceHandle` ve `AfxSetResourceHandle` eski tutamacı kaydedin ve yeni işleyici ayarlayın. İstemci uygulamaya döndüren önce eski kaynağı tanıtıcısı geri emin olun. MFC örneğinde Testdll2 .cpp menü açıkça yüklemek için bu yaklaşımı kullanarak bir örnek için bkz [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk).

MFC nesneleri bir MFC adı verilen dinamik oluşturulmasını benzerdir. MFC nesne seri durumundan çıkarma mekanizması tüm olması gerekiyorsa `CRuntimeClass` nesneleri kayıtlı ne daha önce depolanan üzerinde bağlı olarak gerekli tür C++ nesneleri oluşturarak dinamik olarak yeniden oluşturabilir.

MFC örnek söz konusu olduğunda [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk), liste şöyle görünür:

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

Burada *xx* sürüm numarasıdır; Örneğin, sürüm 4.2 42 temsil eder.

Kaynak ve sınıf listesi genellikle son MFCxx.dll. MFCxx.dll tüm standart komut kimlikleri için komut istemi dizeleri dahil tüm standart MFC kaynakları içerir. Listenin en sonunda yerleştirme, DLL'ler ve kendilerine ait kopyasında standart MFC kaynakları yok ancak MFCxx.dll paylaşılan kaynaklar için bunun yerine dayanır istemci uygulamanın kendisinin sağlar.

Kaynaklar ve sınıf adları tüm DLL'leri, istemci uygulamanın adı alanına birleştirme hangi kimlikleri veya adları ile dikkat gerektiren dezavantajı vardır.

[DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk) örnek paylaşılan kaynak ad alanı birden çok üstbilgi dosyasını kullanarak yönetir.

MFC uzantısı DLL her uygulama için ek verileri tutması gerekiyorsa, yeni bir sınıf türetebilirsiniz **CDynLinkLibrary** ve oluşturun `DllMain`. DLL çalıştırırken, geçerli uygulama listesini denetleyebilirsiniz **CDynLinkLibrary** o belirli MFC uzantısı DLL bulmak için nesneleri.

### <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Bir MFC uzantılı DLL başlatma](run-time-library-behavior.md#initializing-extension-dlls)

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Paylaşılan kaynak dosyalarını kullanma hakkında ipuçları](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)

- [MFC'nin DLL sürümü](../mfc/tn033-dll-version-of-mfc.md)

- [Statik olarak MFC'ye bağlı normal MFC DLL'leri](regular-dlls-statically-linked-to-mfc.md)

- [Dinamik olarak MFC'ye bağlı normal MFC DLL'leri](regular-dlls-dynamically-linked-to-mfc.md)

- [Normal MFC DLL'lerinde Veritabanı, OLE ve Yuva MFC uzantısı DLL'leri Kullanma](using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'da C/C++ DLL'leri oluşturma](dlls-in-visual-cpp.md)
