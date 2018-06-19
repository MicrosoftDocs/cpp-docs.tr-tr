---
title: threadprivate | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- threadprivate
dev_langs:
- C++
helpviewer_keywords:
- threadprivate OpenMP directive
ms.assetid: 3515aaed-6f9d-4d59-85eb-342378bea2d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7e7edaa36f929750087e3c81f42204ff20e9f62
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692918"
---
# <a name="threadprivate"></a>threadprivate
Bir değişken için bir iş parçacığı özel olduğunu belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma omp threadprivate(var)  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Burada,  
  
 `var`  
 Bir iş parçacığı özel yapmak istediğiniz değişkenleri virgülle ayrılmış listesi. `var` Genel veya ad alanı-kapsamlı bir değişken veya yerel bir statik değişken olmalıdır.  
  
## <a name="remarks"></a>Açıklamalar  
 `threadprivate` Yönergesi yok OpenMP yan tümceleri destekler.  
  
 Daha fazla bilgi için bkz: [2.7.1 threadprivate yönergesi](../../../parallel/openmp/2-7-1-threadprivate-directive.md).  
  
 `threadprivate` Yönergesi temel [iş parçacığı](../../../cpp/thread.md) `__declspec` özniteliği; sınırları **__declspec(thread)** uygulamak `threadprivate`.  
  
 Kullanamazsınız `threadprivate` aracılığıyla yüklenen dll [LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175).  Bu ile yüklenen DLL içerir [/DELAYLOAD (yükü içe aktarmayı Geciktir)](../../../build/reference/delayload-delay-load-import.md), kullanan **LoadLibrary**.  
  
 Kullanabileceğiniz `threadprivate` DLL'de işlem başlangıçta statik olarak yüklenir.  
  
 Çünkü `threadprivate` dayanır **__declspec(thread)**, `threadprivate` değişkeni işlemde yalnızca bir paralel bölgeye göre kökenli bir iş parçacığı ekibin parçası olan iş parçacığı çalışmaya herhangi bir iş parçacığı var.  Bu, örneğin, oluşturucuları için fark edebilirsiniz bu yana, bilincinde olmak isteyebilirsiniz bir uygulama ayrıntısı şöyle bir `threadprivate` kullanıcı tanımlı tür genellikle beklenen sonra daha fazla çağrılır.  
  
 A `threadprivate` destructable türünde değişken adında kendi yıkıcı olmasını garanti edilmez.  Örneğin:  
  
```  
struct MyType   
{  
    ~MyType();  
};  
  
MyType threaded_var;  
#pragma omp threadprivate(threaded_var)  
int main()   
{  
    #pragma omp parallel  
    {}  
}  
```  
  
 Kullanıcıların paralel bölge oluşturan iş parçacığı ne zaman sona erdirir konusunda denetim sahibi değildir.  Bu iş parçacığı çıkılıyor, iş parçacıkları hakkında işlem çıkışı bildirilmez ve yıkıcı için çağrılmaz varsa `threaded_var` çıkar dışındaki herhangi bir iş parçacığı üzerinde (burada, birincil iş parçacığı).  Kod uygun yok etme üzerinde güvenmemeniz gerekir olmayan şekilde `threadprivate` değişkenleri.  
  
## <a name="example"></a>Örnek  
 Kullanarak, bir örnek için `threadprivate`, bkz: [özel](../../../parallel/openmp/reference/private-openmp.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler](../../../parallel/openmp/reference/openmp-directives.md)