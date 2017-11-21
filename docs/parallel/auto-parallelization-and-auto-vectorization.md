---
title: "Otomatik Paralelleştirme ve otomatik Vektörleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: ec71583a-287b-4599-8767-1d255e080fe3
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7f84f891a12da90efbe68371d077e2d41b111ea0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="auto-parallelization-and-auto-vectorization"></a>Otomatik Paralelleştirme ve Otomatik Vektörleştirme
Otomatik paralel hale getirici ve otomatik vektör hale getirici otomatik performans artışı kodunuzda döngüler sağlamak için tasarlanmıştır.  
  
## <a name="auto-parallelizer"></a>Otomatik paralel hale getirici  
 [/Qpar](../build/reference/qpar-auto-parallelizer.md) derleyici anahtarı sağlar *otomatik paralelleştirme* döngüsü kodunuzda. Bu bayrak, var olan kodu değiştirmeden belirttiğinizde, derleyici paralelleştirme yararlanabilir döngüler bulmak için kodu değerlendirir. Bul çünkü çok yapmayın döngüler çalışma ve bu nedenle paralelleştirme yararlı olmaz ve her gereksiz paralelleştirme bir iş parçacığı havuzu oluşturma neden olabileceğini çünkü ek eşitleme ya da diğer işleme yavaş eğilimindedir geliştirecek yerine performans, derleyici, parallelizes döngüler seçilmesinde koruyucu. Örneğin, döngü üst sınırının derleme zamanında bilinmiyor aşağıdaki örneği göz önünde bulundurun:  
  
```cpp  
void loop_test(int u) {  
   for (int i=0; i<u; ++i)  
      A[i] = B[i] * C[i];  
}  
```  
  
 Çünkü `u` küçük bir değer olabilir, derleyici otomatik olarak bu döngü paralel hale olmaz. Ancak, yine, paralel birkaç ölçeklendirin, bildiğiniz için isteyebilirsiniz `u` her zaman büyük olacaktır. Otomatik paralelleştirme etkinleştirmek üzere belirtin [#pragma loop(hint_parallel(n))](../preprocessor/loop.md), burada `n` arasında paralel hale iş parçacıklarının sayısıdır. Aşağıdaki örnekte, derleyici döngü 8 iş parçacıkları arasında paralel hale dener.  
  
```cpp  
void loop_test(int u) {  
#pragma loop(hint_parallel(8))  
   for (int i=0; i<u; ++i)  
      A[i] = B[i] * C[i];  
}  
```  
  
 Tümü olduğu gibi [pragma yönergeleri](../preprocessor/pragma-directives-and-the-pragma-keyword.md), alternatif pragma sözdizimi `__pragma(loop(hint_parallel(n)))` da desteklenir.  
  
 İstediğiniz olsa bile, derleyici paralel hale olamaz bazı döngüleri vardır. Örnek buradadır:  
  
```cpp  
#pragma loop(hint_parallel(8))  
for (int i=0; i<upper_bound(); ++i)  
    A[i] = B[i] * C[i];  
```  
  
 İşlev `upper_bound()` her çağrıldığında değişebilir. Üst sınır bilinen çünkü derleyici Bu döngü neden paralel hale olamaz açıklayan bir tanılama iletisi yayma. Aşağıdaki örnek, paralel birkaç ölçeklendirin bir döngü, paralel birkaç ölçeklendirin olamaz bir döngü, komut istemini ve Derleyici çıktısı her komut satırı seçeneği için kullanılacak derleyici sözdizimini gösterir:  
  
```cpp  
int A[1000];  
void test() {  
#pragma loop(hint_parallel(0))  
    for (int i=0; i<1000; ++i) {  
        A[i] = A[i] + 1;  
    }  
  
    for (int i=1000; i<2000; ++i) {  
        A[i] = A[i] + 1;  
    }  
}  
  
```  
  
 Bu komutu kullanarak derleme:  
  
 **cl d:\myproject\mylooptest.cpp O2 /Qpar /Qpar-raporu: 1**  
  
 Bu çıktı üretir:  
  
 **---İşlevi çözümleme: __cdecl test(void) geçersiz kıl**   
 **d:\myproject\mytest.cpp(4): döngü paralel birkaç ölçeklendirin**  
  
 Bu komutu kullanarak derleme:  
  
 **cl d:\myproject\mylooptest.cpp O2 /Qpar /Qpar-raporu: 2**  
  
 Bu çıktı üretir:  
  
 **---İşlevi çözümleme: __cdecl test(void) geçersiz kıl**   
 **d:\myproject\mytest.cpp(4): döngü paralel birkaç ölçeklendirin**   
 **d:\myproject\mytest.cpp(4): döngü '1008' nedenden dolayı paralel birkaç ölçeklendirin değil**  
  
 Çıktı farklı ikisi arasındaki fark [/Qpar-report (otomatik paralel hale getirici raporlama düzeyi)](../build/reference/qpar-report-auto-parallelizer-reporting-level.md) seçenekleri. **/ Qpar-Rapor: 1** başarıyla paralel birkaç ölçeklendirin döngüler için paralel hale getirici iletileri çıkarır. **/ Qpar-Rapor: 2** hem başarılı ve başarısız döngü parallelizations paralel hale getirici iletileri çıkarır.  
  
 Neden kodları ve iletileri hakkında daha fazla bilgi için bkz: [vektör yapıcı ve paralel hale getirici iletileri](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).  
  
## <a name="auto-vectorizer"></a>Otomatik vektör hale getirici  
 Otomatik vektör hale getirici, kodunuzda döngüler analiz eder ve kullanılabiliyorsa vektör kaydeder ve yönergeleri hedef bilgisayar üzerinde bunları yürütmek için kullanır. Bu, kodunuzu performansını artırabilir. Intel ya da AMD işlemcileri SSE2, AVX ve AVX2 yönergeleri veya ARM işlemcileri NEON yönergeler derleyici hedefler göre [/arch](../build/reference/arch-minimum-cpu-architecture.md) geçin.  
  
 Otomatik vektör hale getirici tarafından belirtilenden farklı yönergeleri verebilir **/arch** geçin. Bu yönergeler, kod hala düzgün çalıştığından emin olmak için bir çalışma zamanı denetimi tarafından korumalı. Ne zaman derleme, örneğin, **/arch:SSE2**, SSE4.2 yönergeleri yayılan. Bir çalışma zamanı denetim SSE4.2 hedef işlemci kullanılabilir olduğunu ve işlemci bu yönergeleri desteklemiyorsa, döngü SSE4.2 olmayan sürümüne atlar olduğunu doğrular.  
  
 Varsayılan olarak otomatik vektör hale getirici etkindir. Kodunuzu vectorization altında performans karşılaştırma yapmak isterseniz, kullanabileceğiniz [#pragma loop(no_vector)](../preprocessor/loop.md) vectorization herhangi verilen döngüsü devre dışı bırakmak için.  
  
```  
  
      #pragma loop(no_vector)  
for (int i = 0; i < 1000; ++i)  
   A[i] = B[i] + C[i];  
  
```  
  
 Tümü olduğu gibi [pragma yönergeleri](../preprocessor/pragma-directives-and-the-pragma-keyword.md), alternatif pragma sözdizimi `__pragma(loop(no_vector))` da desteklenir.  
  
 Otomatik paralel hale getirici ile belirttiğiniz gibi [/Qvec-report (otomatik vektör hale getirici raporlama düzeyi)](../build/reference/qvec-report-auto-vectorizer-reporting-level.md) ya da başarılı bir şekilde bildirmek için komut satırı seçeneği yalnızca döngüler vectorized —**/Qvec-raporu: 1**— veya başarılı ve başarısız vectorized döngüler —**/Qvec-raporu: 2**).  
  
 Neden kodları ve iletileri hakkında daha fazla bilgi için bkz: [vektör yapıcı ve paralel hale getirici iletileri](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).  
  
 Vektör yapıcı uygulamada nasıl çalıştığını gösteren bir örnek için bkz: [proje Ankara'da Kısım 2 / 6: sayfa Curling](http://blogs.msdn.com/b/vcblog/archive/2012/09/27/10348494.aspx)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [döngü](../preprocessor/loop.md)   
 [Yerel kodda paralel programlama](http://go.microsoft.com/fwlink/?linkid=263662)   
 [/ Qpar (otomatik paralel hale getirici)](../build/reference/qpar-auto-parallelizer.md)   
 [/ Qpar (otomatik paralel hale getirici düzeyi raporlama) raporu](../build/reference/qpar-report-auto-parallelizer-reporting-level.md)   
 [/ Qvec-(Raporlama düzeyi otomatik vektör hale getirici) raporu](../build/reference/qvec-report-auto-vectorizer-reporting-level.md)   
 [Vektör yapıcı ve paralel hale getirici iletileri](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)