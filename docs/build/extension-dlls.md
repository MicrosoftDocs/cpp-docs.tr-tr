---
title: "Uzantı DLL'leri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: afxdll
dev_langs: C++
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
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 45e94997dbeb2c6413ffcdc1272a3a46a7e220ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-extension-dlls"></a>MFC uzantı DLL'leri
MFC uzantı DLL'si genellikle mevcut Microsoft Foundation Class Kitaplığı sınıflarından türetilmiş yeniden kullanılabilir sınıfları uygulayan bir DLL'dir.  
  
 MFC uzantı DLL'si, aşağıdaki özellikler ve gereksinimler vardır:  
  
-   İstemci yürütülebilir ile derlenen bir MFC uygulaması olmalıdır `_AFXDLL` tanımlanmış.  
  
-   MFC uzantı DLL'si, dinamik olarak MFC'ye bağlı normal bir MFC DLL tarafından da kullanılabilir.  
  
-   MFC uzantı DLL'leri ile derlenmelidir `_AFXEXT` tanımlanmış. Bu zorlar `_AFXDLL` de tanımlanmasını ve uygun bildirimlerin çekilmesini MFC başlık dosyalarından sağlar. Ayrıca, sağlar `AFX_EXT_CLASS` olarak tanımlanan `__declspec(dllexport)` DLL derlenirken hatalarla olduğu sınıflar, MFC uzantı DLL'si bildirmek için bu makrosu kullanıyorsanız, gerekli.  
  
-   MFC uzantı DLL'leri türetilmiş bir sınıf oluşturmamalı `CWinApp`, ancak istemci uygulaması (veya DLL) bu nesneyi sağlamak için yararlanmalıdır.  
  
-   MFC uzantı DLL'leri ancak sağlaması bir `DllMain` işlev ve gerekli sıfırlamaları var. yapın.  
  
 Uzantı DLL'leri MFC'nin (olarak da bilinen MFC paylaşılan sürüm) dinamik bağlantı kitaplığı sürümü kullanılarak oluşturulur. MFC uzantı DLL'si MFC paylaşılan sürümü ile oluşturulan yalnızca MFC yürütülebilir dosyaları (uygulamalar veya Normal MFC DLL'leri) kullanabilirsiniz. İstemci uygulaması ve MFC uzantı DLL'si MFCx0.dll aynı sürümünü kullanmanız gerekir. MFC DLL uzantısı ile yeni özel sınıflar türetebilir ve ardından bu genişletilmiş sürümüne MFC DLL çağıran uygulamalar sunar.  
  
 Uzantı DLL'leri de uygulama ve DLL arasında MFC'den türetilen nesneleri geçirmek için kullanılabilir. Geçirilen nesneyle ilişkili üye işlevleri nesne oluşturulduğu modülünde mevcut. Bu işlevler düzgün paylaşılan MFC'nin DLL sürümü kullanılırken dışarı aktarıldığı için MFC serbestçe geçirebilir veya uygulama ve MFC uzantı DLL'leri arasında MFC türetilmiş nesne işaretçileri.  
  
 MFC uzantı DLL'si MFC'nin paylaşılan sürümü uygulama MFC, paylaşılan DLL sürümü ile birkaç ek hususlar kullanan aynı şekilde kullanır:  
  
-   Sahip olmayan bir `CWinApp`-türetilmiş bir nesne içermelidir. Birlikte çalışmalısınız `CWinApp`-nesne istemci uygulamasının türetilmiş. Bu, istemci uygulaması ana ileti göndericisi, boşta döngü ve benzeri sahibi olduğu anlamına gelir.  
  
-   Çağırır `AfxInitExtensionModule` içinde kendi `DllMain` işlevi. Bu işlevin dönüş değeri denetlenmesi. Sıfır değeri döndürdüyse `AfxInitExtensionModule`, 0'dan iade, `DllMain` işlevi.  
  
-   Oluşturduğu bir **CDynLinkLibrary** MFC uzantı DLL vermek istediğinde, başlatma sırasında nesne `CRuntimeClass` nesneleri veya kaynakları uygulamaya.  
  
 MFC 4.0 sürümünden önce bu tür DLL AFXDLL çağrıldı. AFXDLL başvurduğu `_AFXDLL` DLL oluşturulurken tanımlanan önişlemci sembolü.  
  
 MFC paylaşılan sürümü için içeri aktarma kitaplıkları açıklanan kurala göre adlandırılır [MFC DLL'leri için adlandırma kuralları](../build/naming-conventions-for-mfc-dlls.md). Visual C++ MFC DLL'leri yanı sıra, bir sayı, MFC dışı kullanan ve uygulamalarınızı dağıtma DLL'ler önceden oluşturulmuş sürümlerini sağlar. Bu Program Files\Microsoft Visual Studio klasörüne yüklenir Redist.txt'e belgelenmiştir.  
  
 .Def dosyası kullanarak dışa aktarıyorsanız, aşağıdaki kod, üstbilgi dosyası başında ve sonunda yerleştir:  
  
```cpp  
#undef AFX_DATA  
#define AFX_DATA AFX_EXT_DATA  
// <body of your header file>  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
 Bu dört satırı kodunuzun doğru MFC uzantı DLL için derlenmiş emin olun. Bu dört satırı dışarıda bırakarak derleme ya da yanlış bağlamak için DLL neden olabilir.  
  
 Bir MFC geçirmenize gerek isterseniz MFC türetilmiş nesne işaretçisi için veya bir MFC DLL, DLL MFC uzantı DLL'si olmalıdır. Geçirilen nesneyle ilişkili üye işlevleri nesne oluşturulduğu modülünde mevcut. Bu işlevler düzgün paylaşılan MFC'nin DLL sürümü kullanılırken dışarı aktarıldığı için MFC serbestçe geçirebilir veya uygulama ve MFC uzantı DLL'leri arasında MFC türetilmiş nesne işaretçileri.  
  
 C++ ad bozma ve dışarı aktarma sorunları nedeniyle, dışarı aktarma listesi MFC uzantı DLL farklı platform için aynı DLL hata ayıklama ve perakende sürümleri ve DLL'ler farklı olabilir. Perakende MFCx0.dll yaklaşık 2.000 dışarı aktarılan giriş noktası; hata MFCx0D.dll yaklaşık 3000 dışarı aktarılan giriş noktası vardır.  
  
## <a name="memory-management"></a>Bellek Yönetimi  
 Aynı uygulamada değilmiş gibi MFCx0.dll ve tüm MFC uzantı DLL'leri istemci uygulamanın adres alanına yüklenen aynı bellek ayırıcısı, kaynak yükleme ve diğer MFC genel durumlarını kullanır. MFC DLL kitaplıkları ve Normal MFC DLL'leri tam tersi yapın ve her DLL ayırma, kendi bellek havuzunda yetersiz olması gerektiğinden, bu önemlidir.  
  
 MFC uzantı DLL'si bellek ayırır, bu bellek diğer uygulama ayrılan nesneleri serbestçe intermix. Ayrıca, dinamik olarak MFC'ye bağlanan bir uygulama başarısız olursa, işletim sisteminin koruma DLL paylaşımı başka bir MFC Uygulama bütünlüğünü korur.  
  
 Benzer şekilde, kaynakları yüklemek için geçerli yürütülebilir dosya gibi diğer global MFC durumları da istemci uygulaması ve tüm MFC uzantı DLL'leri yanı sıra arasında MFCx0.dll kendisini paylaşılır.  
  
## <a name="sharing-resources-and-classes"></a>Kaynakları ve sınıfları paylaşma  
 Kaynakları dışarı aktarma, bir kaynak listesi üzerinden yapılır. Her uygulama tek bağlı bir listesini içeren **CDynLinkLibrary** nesneleri. Bir kaynak ararken kaynakları yükleyen standart MFC uygulamalarının çoğunu geçerli kaynak modülüne bakar (`AfxGetResourceHandle`) ve kaynak bulunmazsa yol listesi **CDynLinkLibrary** nesneleri İstenen kaynak yüklenmeye çalışılıyor.  
  
 Listenin taramasını kısmen daha yavaştır ve kaynak kimlik aralıklarını yönetmeyi gerektirir dezavantajları vardır. Birkaç MFC uzantı DLL'leri bağlanan istemci uygulaması herhangi bir DLL tarafından sağlanan kaynak DLL örneği işleyicisi belirtmek zorunda kalmadan kullanabileceğiniz avantajına sahiptir. `AfxFindResourceHandle`bir API, belirli bir eşleşme için aranacak kaynak listesi taramasını için kullanılır. Bir kaynak türü ve adını alır ve ilk bulunduğu kaynak tanıtıcısı (veya NULL) döndürür.  
  
 Listeyi izlemek ve yalnızca belirli bir konumdan kaynakları yüklemek istemiyorsanız işlevleri kullanmak `AfxGetResourceHandle` ve `AfxSetResourceHandle` eski tutamacı kaydedip yeni tutamacı ayarlayın. İstemci uygulamasına geri dönmeden önce eski kaynak tanıtıcısını geri yüklediğinizden emin olun. MFC örnekteki Testdll2 .cpp açıkça bir menü yüklemek için bu yaklaşımı kullanarak, bir örnek için bkz: [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk).  
  
 MFC nesneleri bir MFC adı verilen dinamik oluşturulmasını benzer. MFC nesne seri durumdan çıkarma mekanizması tümüne sahip olması `CRuntimeClass` nesneleri kaydedilen dinamik olarak ne daha önce depolanan üzerinde bağlı olarak gerekli tür C++ nesnelerini oluşturarak yeniden.  
  
 MFC örnek durumunda [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk), liste şöyle görünür:  
  
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
  
 Burada *xx* sürüm numarası; Örneğin, sürüm 4.2 42 temsil eder.  
  
 MFCxx.dll kaynak ve sınıf listesi genellikle son. MFCxx.dll tüm standart komut kimlikleri için komut istemi dizeleri dahil tüm standart MFC kaynakları içerir. Listesinin sonuna yerleştirme DLL'ler ve standart MFC kaynakları kendi kopyasına sahip değildir ancak bunun yerine MFCxx.dll paylaşılan kaynakları kullanır istemci uygulamanın kendisinin sağlar.  
  
 İstemci uygulamanın ad alanına birleştirme kaynakları ve sınıf adlarını tüm DLL'ler hangi kimlikleri ve adları dikkatli olun gerek dezavantajı vardır.  
  
 [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk) örnek birden çok başlık dosyalarını kullanarak paylaşılan kaynak ad alanı yönetir.  
  
 MFC uzantı DLL'si her uygulama için ek veri tutması gerekiyorsa, yeni bir sınıf türetin **CDynLinkLibrary** ve içinde oluşturun `DllMain`. Çalıştırırken, DLL geçerli uygulama listesini denetleyebilirsiniz **CDynLinkLibrary** belirli MFC uzantısı DLL bulmak için nesneleri.  
  
### <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?  
  
-   [MFC uzantı DLL başlatma](../build/run-time-library-behavior.md#initializing-extension-dlls)  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [Paylaşılan kaynak dosyalarını kullanma ile ilgili ipuçları](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)  
  
-   [MFC'nin DLL sürümü](../mfc/tn033-dll-version-of-mfc.md)  
  
-   [Statik olarak MFC'ye bağlı normal MFC DLL'leri](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [Dinamik olarak MFC'ye bağlı normal MFC DLL'leri](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [Normal MFC DLL'lerinde Veritabanı, OLE ve Yuva MFC uzantısı DLL'leri Kullanma](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++'ta DLL'ler](../build/dlls-in-visual-cpp.md)