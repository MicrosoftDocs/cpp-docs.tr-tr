---
title: "Çoklu iş parçacığı kullanımı: MFC'yi çalışan iş parçacıkları oluşturma | Microsoft Docs"
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- multithreading [C++], worker threads
- background tasks [C++]
- threading [C++], worker threads
- worker threads [C++]
- threading [C++], creating threads
- threading [MFC], worker threads
- threading [C++], user input not required
ms.assetid: 670adbfe-041c-4450-a3ed-be14aab15234
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90e0af6a1b11b114e56e6c1d87cb293ab83dd768
ms.sourcegitcommit: f7703076b850c717c33d72fb0755fbb2215c5ddc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/28/2018
ms.locfileid: "43131195"
---
# <a name="multithreading-creating-worker-threads-in-mfc"></a>Çoklu iş parçacığı kullanımı: MFC'yi çalışan iş parçacıkları oluşturma
İş parçacığı, kullanıcının uygulamanızı kullanmaya devam etmek için beklenecek olmaması gereken arka plan görevlerinin işlenmesi için yaygın olarak kullanılır. Yeniden hesaplama ve arka plan yazdırma gibi görevler, çalışan iş parçacıkları, iyi örneklerdir. Bu konu bir iş parçacığı oluşturmak gerekli adımları ayrıntılı olarak açıklanmaktadır. Konular şunlardır:  
  
- [İş parçacığını başlatma](#_core_starting_the_thread)  
  
- [Denetim işlevini uygulama](#_core_implementing_the_controlling_function)  
  
- [Örnek](#_core_controlling_function_example)  
  
Bir iş parçacığı oluşturmak göreceli olarak basit bir görevdir. İş parçacığınızın için yalnızca iki adım gereklidir: denetleme işlevini uygulamak ve iş parçacığı başlatılıyor. Öğesinden bir sınıf türetmek gerekli değil [CWinThread](../mfc/reference/cwinthread-class.md). Özel bir sürümünü gerekiyorsa bir sınıf türetebilirsiniz `CWinThread`, ancak en basit çalışan iş parçacıkları için gerekli değildir. Kullanabileceğiniz `CWinThread` yapmadan.  
  
##  <a name="_core_starting_the_thread"></a> İş parçacığını başlatma  
 
İki aşırı yüklenmiş sürümleri `AfxBeginThread`: yalnızca çalışan iş parçacıkları oluşturabilirsiniz ve hem kullanıcı arabirimi iş parçacıkları ve çalışan iş parçacıkları oluşturabilirsiniz. İlk aşırı yükleme kullanarak, çalışan iş parçacığının yürütülmesini başlatmak için çağrı [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), aşağıdaki bilgileri sağlayarak:  
  
- Denetleme işlevi adresi.  
  
- Denetim işlevine iletilecek parametre.  
  
- (İsteğe bağlı) İş parçacığının istenen önceliği. Varsayılan, normal önceliktir. Kullanılabilir öncelik düzeyleri hakkında daha fazla bilgi için bkz: [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) Windows SDK.  
  
- (İsteğe bağlı) İş parçacığının istenen yığın boyutu. Oluşturulan iş parçacığıyla aynı boyutta bir yığına varsayılandır.  
  
- (İsteğe bağlı) CREATE_SUSPENDED iş parçacığının askıya alınmış durumda oluşturulmasını istiyorsanız. Varsayılan, 0 veya iş parçacığını normal olarak başlatın.  
  
- (İsteğe bağlı) İstenen güvenlik öznitelikleri. Varsayılan ana iş parçacığıyla aynı erişimdir. Bu güvenlik bilgileri biçimi hakkında daha fazla bilgi için bkz. [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) Windows SDK.  
  
`AfxBeginThread` oluşturur ve başlatır bir `CWinThread` sizin için nesne başlar ve, daha sonra başvurduğu için adresini döndürür. Denetimleri, tüm nesnelerin düzgün bir şekilde oluşturmayı, herhangi bir bölümü başarısız olması serbest bırakıldığından emin olmak için yordam boyunca gerçekleştirilir.  
  
##  <a name="_core_implementing_the_controlling_function"></a> Denetim işlevini uygulama  
 
Denetleme işlevi iş parçacığını tanımlar. Bu işlev girildiğinde, iş parçacığı başlatılır ve çıktığında iş parçacığı sonlanır. Bu işlev, aşağıdaki prototipi içermelidir:  
  
```  
UINT MyControllingFunction( LPVOID pParam );  
```  
  
Parametre tek bir değerdir. Bu parametrede işlevin aldığı değer, iş parçacığı nesnesi oluşturulduğunda oluşturucuya geçirilen değerdir. Denetleme işlevi bu değeri seçtiği herhangi bir şekilde yorumlayabilir. Skaler değer ya da birden çok parametre içeren bir yapıya bir işaretçi olarak kabul ya da sayılabilir. Parametre bir yapıya başvurursa, yapı yalnızca arayandan iş parçacığına veri geçirmek, aynı zamanda veri iş parçacığından arayana iletmek için kullanılabilir. Böyle bir yapı çağırana geri veri aktarmak için kullanırsanız, iş parçacığı sonuçlar hazır olduğunda çağrıyı yapana bunu bildirmesi gerekir. Çalışan iş parçacığından arayana iletişim hakkında daha fazla bilgi için bkz: [çoklu iş parçacığı kullanımı: programlama ipuçları](multithreading-programming-tips.md).  
  
İşlev sonlandığında, sonlandırma nedenini belirten bir UINT değeri döndürmesi gerekir. Genellikle bu çıkış kodu farklı hatalar gösteren diğer değerler ile başarıyı belirtmek için 0'dır. Tamamen uygulamaya bağlıdır budur. Bazı iş parçacıkları nesnelerin kullanım sayısını korumak ve o nesnenin kullanan geçerli sayısını döndürür. Uygulamalar bu değeri nasıl alabildiğini görmek için bkz: [çoklu iş parçacığı kullanımı: iş parçacıklarını sonlandırma](multithreading-terminating-threads.md).  
  
MFC kitaplığı ile yazılan çoklu iş parçacığı kullanan programda yapabilecekleriniz bazı kısıtlamalar vardır. Bu kısıtlamalar ve iş parçacığı kullanma hakkında diğer ipuçları açıklamaları için bkz. [çoklu iş parçacığı kullanımı: programlama ipuçları](multithreading-programming-tips.md).  
  
##  <a name="_core_controlling_function_example"></a> Denetleme işlevi örneği  
 
Aşağıdaki örnek, bir denetleyen işlevin tanımlamak ve başka bir program bölümünden kullanma gösterilmektedir.  
  
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
  
- [Çoklu İş Parçacığı Kullanımı: Kullanıcı Arabirimi İş Parçacıkları Oluşturma](multithreading-creating-user-interface-threads.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[C++ ve MCF ile Çoklu İş Parçacığı Kullanımı](multithreading-with-cpp-and-mfc.md)