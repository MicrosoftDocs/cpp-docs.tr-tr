---
title: Vadeli. 2\.0 sürümündeki yeni özellikler ve açıklamalar
ms.date: 01/22/2019
ms.assetid: 0d4beb66-f2d5-468c-8cd3-4b00dcbab061
ms.openlocfilehash: 8cd82000992ab957bf2c41f11deccd65e2e6ea8f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80215039"
---
# <a name="f-new-features-and-clarifications-in-version-20"></a>Vadeli. 2\.0 sürümündeki yeni özellikler ve açıklamalar

Bu ekte, 1,0 sürümünden sürüm 2,0 ' den geçiş yaparken OpenMPC++ C/belirtiminde yapılan önemli değişiklikler özetlenmektedir. Aşağıdaki öğeler, belirtime eklenen yeni özelliklerdir:

- OpenMP [yönergelerinde](2-directives.md#21-directive-format)virgüller kullanılabilir.

- `num_threads` yan tümcesinin eklenmesi. Bu yan tümce, bir kullanıcının [paralel bir yapı](2-directives.md#23-parallel-construct)için belirli sayıda iş parçacığı istemesine izin verir.

- [Threadprivate](2-directives.md#271-threadprivate-directive) yönergesi statik blok kapsamı değişkenlerini kabul edecek şekilde genişletildi.

- C99 değişken uzunluğu dizileri, tüm türlerdir ve `private`, `firstprivate`ve `lastprivate` yan tümceleri listelerinde (bkz. [Section 2.7.2](2-directives.md#272-data-sharing-attribute-clauses)) her yerde,

- Bir paralel bölgedeki özel değişken, iç içe bir yönergede [özel](2-directives.md#2721-private) olarak yeniden işaretlenebilir.

- `copyprivate` yan tümcesi eklenmiştir. Bir ekibin bir üyesinden diğer üyelere bir değer yayınlamak için özel bir değişken kullanmak için bir mekanizma sağlar. Bu tür paylaşılan bir değişkenin sağlanması zor olur (örneğin, her düzeyde farklı bir değişken gerektiren bir özyineleme). [Copyprivate](2-directives.md#2728-copyprivate) yan tümcesi yalnızca `single` yönergesinde bulunabilir.

- [Omp_get_wtick](3-run-time-library-functions.md#332-omp_get_wtick-function) ve [omp_get_wtime](3-run-time-library-functions.md#331-omp_get_wtime-function) MPI yordamlarına benzer zamanlama yordamlarını ekleme. Bu işlevler, duvar saati zamanlamalarını yapmak için gereklidir.

- OpenMP C/C++ içindeki [uygulama tanımlı davranışların](e-implementation-defined-behaviors-in-openmp-c-cpp.md) listesini içeren bir ek eklenmiştir. Bu durumlarda davranışını tanımlamak ve belgelemek için bir uygulama gerekir.

- Aşağıdaki değişiklikler C/C++Için ÖNCEKI OpenMP API belirtiminde bulunan özellikleri açıklığa kavuşturmanıza veya gidermeye yöneliktir:

  - `omp_in_parallel` sıfır dışında bir değer döndürüldüğünde [omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function) ve [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) davranışının tanımsız olduğunu açıklığa kavuşturuldu.

  - İç içe paralel kullanıldığında, açıklanan [Yönerge iç](2-directives.md#29-directive-nesting) içe kullanılıyor.

  - [Kilit başlatma](3-run-time-library-functions.md#321-omp_init_lock-and-omp_init_nest_lock-functions) ve [kilit yok etme](3-run-time-library-functions.md#322-omp_destroy_lock-and-omp_destroy_nest_lock-functions) işlevleri bir paralel bölgede çağrılabilir.

  - [Ek A](a-examples.md)'ya yeni örnekler eklenmiştir.
