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
ms.openlocfilehash: a9313934744f6eae66736f25b0d0b8592743cf12
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376986"
---
# <a name="threadprivate"></a>threadprivate

Bir değişken için bir iş parçacığı özel olduğunu belirtir.

## <a name="syntax"></a>Sözdizimi

```
#pragma omp threadprivate(var)
```

### <a name="parameters"></a>Parametreler

*var*<br/>
Bir iş parçacığına özel yapmak istediğiniz değişkenleri virgülle ayrılmış listesi. `var` Genel veya ad alanı-kapsamlı bir değişken veya yerel bir statik değişken olmalıdır.

## <a name="remarks"></a>Açıklamalar

`threadprivate` Yönergesi yok OpenMP yan tümceleri destekler.

Daha fazla bilgi için [2.7.1 threadprivate yönergesi](../../../parallel/openmp/2-7-1-threadprivate-directive.md).

`threadprivate` Yönergesi temel [iş parçacığı](../../../cpp/thread.md) `__declspec` öznitelik; barındırabileceğiniz **gt;__declspec(thread)** uygulamak `threadprivate`.

Kullanamazsınız `threadprivate` aracılığıyla yüklenen herhangi bir DLL içinde [LoadLibrary](https://msdn.microsoft.com/library/windows/desktop/ms684175).  Bu ile yüklenen DLL'ler içerir [/delayload (gecikme yükü içe)](../../../build/reference/delayload-delay-load-import.md), kullanan **LoadLibrary**.

Kullanabileceğiniz `threadprivate` işlem başlangıçta statik olarak yüklenen bir DLL içinde.

Çünkü `threadprivate` dayanır **gt;__declspec(thread)**, `threadprivate` değişkeni işlemde yalnızca bir paralel bölgenin tarafından üretilen bir iş parçacığı ekibin parçası olan iş parçacığı çalışmaya herhangi bir iş parçacığı var.  Bu, örneğin, Oluşturucular için fark edebilirsiniz olduğundan, dikkat edilmesi gereken isteyebileceğiniz bir uygulama ayrıntısı olan bir `threadprivate` genellikle beklenen sonra daha fazla kullanıcı tanımlı tür adı.

A `threadprivate` destructable türünde değişken adında yok edici olmasını garanti edilmez.  Örneğin:

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

Kullanıcılar için bir paralel bölgenin oluşturan iş parçacıklarının ne zaman sona erer denetiminiz yoktur.  Bu iş parçacıkları işlemi, iş parçacıkları hakkında işlem çıkış bildirilmez ve yok edici için çağrılmayacak varsa `threaded_var` çıkar dışındaki herhangi bir iş parçacığı üzerinde (burada, birincil iş parçacığı).  Kod üzerinde uygun edilmesine sayısı değil şekilde `threadprivate` değişkenleri.

## <a name="example"></a>Örnek

Kullanarak bir örnek için `threadprivate`, bkz: [özel](../../../parallel/openmp/reference/private-openmp.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Yönergeler](../../../parallel/openmp/reference/openmp-directives.md)