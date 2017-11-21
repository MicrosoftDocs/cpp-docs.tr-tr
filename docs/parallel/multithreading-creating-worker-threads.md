---
title: "Çoklu iş parçacığı kullanımı: Çalışan iş parçacıkları oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- multithreading [C++], worker threads
- background tasks [C++]
- threading [C++], worker threads
- worker threads [C++]
- threading [C++], creating threads
- threading [MFC], worker threads
- threading [C++], user input not required
ms.assetid: 670adbfe-041c-4450-a3ed-be14aab15234
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c43b8453b592369d8179c9d3917bdbcc7381fa00
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="multithreading-creating-worker-threads"></a>Çoklu İş Parçacığı Kullanımı: Çalışan İş Parçacıkları Oluşturma
Bir çalışan iş parçacığı yaygın kullanıcı uygulamanızı kullanmaya devam etmek için beklemek için olmamalıdır arka plan görevlerini işlemek için kullanılır. Yeniden hesaplama ve arka plan yazdırma gibi görevleri çalışan iş parçacığı iyi örnekleridir. Bu konuda, bir çalışan iş parçacığı oluşturmak için gerekli adımları ayrıntıları verilmektedir. Konular şunlardır:  
  
-   [İş parçacığı başlatılıyor](#_core_starting_the_thread)  
  
-   [Denetim işlevini uygulama](#_core_implementing_the_controlling_function)  
  
-   [Örnek](#_core_controlling_function_example)  
  
 Bir çalışan iş parçacığı oluşturma oldukça basit bir görevdir. Yalnızca iki adım çalıştıran, iş parçacığı almak için gereklidir: denetleme işlevini uygulamak ve iş parçacığı başlatılıyor. Öğesinden bir sınıf türetin gerekli değildir [CWinThread](../mfc/reference/cwinthread-class.md). Özel bir sürümü gerekiyorsa bir sınıf türetin `CWinThread`, ancak çoğu basit çalışan iş parçacığı için gerekli değildir. Kullanabileceğiniz `CWinThread` değişiklik yapmadan.  
  
##  <a name="_core_starting_the_thread"></a>İş parçacığı başlatılıyor  
 Aşırı yüklenmiş iki sürümü vardır `AfxBeginThread`: yalnızca çalışan iş parçacığı oluşturabilir ve kullanıcı arabirimi iş parçacıkları ve iş parçacıklarını oluşturabilirsiniz. Çalışan iş parçacığı ilk aşırı yüklemeleri kullanarak yürütülmesi başlamak için arama [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), aşağıdaki bilgileri sağlar:  
  
-   Denetleyen işlev adresi.  
  
-   Denetleyen işlev iletilecek parametre.  
  
-   (İsteğe bağlı) İş parçacığı istenen önceliği. Normal öncelikli varsayılandır. Varolan öncelik düzeyleri hakkında daha fazla bilgi için bkz: [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) içinde [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
-   (İsteğe bağlı) İş parçacığı için istenen yığın boyutu. Aynı boyut yığın oluşturma iş parçacığı olarak varsayılandır.  
  
-   (İsteğe bağlı) **AfxBeginThread'e** askıya alınmış durumda oluşturulacak iş parçacığı istiyorsanız. Varsayılan değer 0'dır veya normal iş parçacığı başlatılamıyor.  
  
-   (İsteğe bağlı) İstenen güvenlik öznitelikleri. Üst iş parçacığı aynı erişim varsayılandır. Bu güvenlik bilgileri biçimi hakkında daha fazla bilgi için bkz: [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) içinde [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
 `AfxBeginThread`oluşturur ve başlatır bir `CWinThread` nesnesi, başlar ve böylece için daha sonra başvurabilirsiniz adresini döndürür. Denetimleri prosedür boyunca tüm nesneleri düzgün herhangi bir kısmını oluşturma başarısız olması kaldırıldığından emin olmak için yapılır.  
  
##  <a name="_core_implementing_the_controlling_function"></a>Denetim işlevini uygulama  
 İş parçacığı denetim işlevini tanımlar. Bu işlev girildiğinde, iş parçacığı başlar ve çıktığında, iş parçacığı sonlanır. Bu işlevi aşağıdaki prototipi içermelidir:  
  
```  
UINT MyControllingFunction( LPVOID pParam );  
```  
  
 Tek bir değer parametresidir. Bu parametrede işlevi alır değer iş parçacığı nesnesi oluşturulduğunda, oluşturucuya geçirilen değerdir. Denetleyen işlev, bu değeri seçtiği herhangi bir şekilde çevirebilir. Skaler değer veya birden çok parametre içeren bir yapı için bir işaretçi olarak kabul veya göz ardı. Parametre bir yapıya başvuruyorsa, yapısı değil yalnızca iş parçacığına çağrıyı yapandan veri iletmek için aynı zamanda iş parçacığından arayana veri iletmek için kullanılabilir. Geri çağırana veri iletmek için böyle bir yapı kullanırsanız, iş parçacığı sonuçları hazır olduğunuzda, çağıran bildirmesi gerekir. Çalışan iş parçacığından arayana iletişim hakkında daha fazla bilgi için bkz: [çoklu iş parçacığı kullanımı: programlama ipuçları](../parallel/multithreading-programming-tips.md).  
  
 İşlev sonlandırıldığında döndürmelidir bir **UINT** sonlandırma nedenini belirten değer. Genellikle, bu çıkış kodu farklı türdeki hatalar gösteren diğer değerler ile başarılı olduğunu belirtmek için 0'dır. Bu tamamen bağımlı uygulamasıdır. Bazı iş parçacıkları nesnelerin kullanım sayısını korumak ve söz konusu nesne kullanımları geçerli sayısını döndür. Bu değer uygulamaları nasıl alabildiğini görmek için bkz: [çoklu iş parçacığı kullanımı: iş parçacıklarını sonlandırma](../parallel/multithreading-terminating-threads.md).  
  
 MFC kitaplığı ile yazılmış birden çok iş parçacıklı bir program yapabilecekleriniz bazı kısıtlamalar vardır. Bu kısıtlamalar ve iş parçacığı kullanma hakkında diğer ipuçları açıklamaları için bkz: [çoklu iş parçacığı kullanımı: programlama ipuçları](../parallel/multithreading-programming-tips.md).  
  
##  <a name="_core_controlling_function_example"></a>Denetleme işlevi örneği  
 Aşağıdaki örnek, denetleyen işlev tanımlama ve başka bir program bölümünden kullanma gösterilmektedir.  
  
```  
UINT MyThreadProc( LPVOID pParam )  
{  
    CMyObject* pObject = (CMyObject*)pParam;  
  
    if (pObject == NULL ||  
        !pObject->IsKindOf(RUNTIME_CLASS(CMyObject)))  
    return 1;   // if pObject is not valid  
  
    // do something with 'pObject'  
  
    return 0;   // thread completed successfully  
}  
  
// inside a different function in the program  
.  
.  
.  
pNewObject = new CMyObject;  
AfxBeginThread(MyThreadProc, pNewObject);  
.  
.  
.  
```  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [Çoklu iş parçacığı kullanımı: Kullanıcı arabirimi iş parçacıkları oluşturma](../parallel/multithreading-creating-user-interface-threads.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ ve MCF ile çoklu iş parçacığı kullanımı](../parallel/multithreading-with-cpp-and-mfc.md)