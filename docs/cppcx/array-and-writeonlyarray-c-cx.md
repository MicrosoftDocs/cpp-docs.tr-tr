---
title: Dizi ve WriteOnlyArray (C++/CX)
ms.date: 01/22/2017
ms.assetid: ef7cc5f9-cae6-4636-8220-f789e5b6aea4
ms.openlocfilehash: e050fad38d4f70c651fc0ebfddb51a33e31da6f3
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032414"
---
# <a name="array-and-writeonlyarray-ccx"></a>Dizi ve WriteOnlyArray (C++/CX)

C++/CX programında [(std::vector](../standard-library/vector-class.md) genellikle daha iyi bir seçim olsa da) normal C stili dizileri veya [std::diziyi](../standard-library/array-class-stl.md) serbestçe kullanabilirsiniz, ancak meta verilerde yayınlanan herhangi bir API'de, C stili bir diziyi veya vektörü platforma dönüştürmeniz [gerekir::Dizi](../cppcx/platform-array-class.md) veya [Platform::Nasıl](../cppcx/platform-writeonlyarray-class.md) kullanıldığına bağlı olarak WriteOnlyArray türü. [Platform::Dizi](../cppcx/platform-array-class.md) türü ne std kadar verimli ne de std kadar [güçlüdür::vektör,](../standard-library/vector-class.md)bu nedenle genel bir kılavuz olarak dizi öğeleri üzerinde çok sayıda işlem gerçekleştiren iç kodda kullanılmasını önlemeniz gerekir.

Aşağıdaki dizi türleri ABI üzerinden geçirilebilir:

1. const Platform::Dizi^

1. Platform::Dizi^*

1. Platform::WriteOnlyArray

1. Platformun iade değeri::Array^

Bu dizi türlerini, Windows Runtime tarafından tanımlanan üç tür dizi deseni uygulamak için kullanırsınız.

PassArray Arayan bir diziyi bir metyönteme geçtiğinde kullanılır. C++ giriş parametresi `const`türü [Platform::Array](../cppcx/platform-array-class.md)\<T>.

FillArray Arayanın doldurması için yöntem için bir dizi geçtiğinde kullanılır. C++ giriş parametresi türü [Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md)\<T>.

ReceiveArray Arayanın yöntemin ayırdığı bir dizi aldığında kullanılır. C++/CX'te diziyi dönüş değerindebir Dizi^ olarak döndürebilir veya dizi tipi^* olarak dış parametre olarak döndürebilirsiniz.

## <a name="passarray-pattern"></a>PassArray deseni

İstemci kodu bir diziyi C++ yöntemine aktardığında ve yöntem onu değiştirmediğinde, yöntem diziyi const Dizi^ olarak kabul eder. Windows Runtime uygulama ikili arabirimi (ABI) düzeyinde, bu bir PassArray olarak bilinir. Sonraki örnek, JavaScript'te ayrılan bir dizinin ondan okuyan bir C++ işlevine nasıl geçirilebildiğini gösterir.

[!code-javascript[cx_arrays#101](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_1.js)]

Aşağıdaki parçacık C++ yöntemini gösterir:

[!code-cpp[cx_arrays#01](../cppcx/codesnippet/CPP/js-array/class1.cpp#01)]

## <a name="receivearray-pattern"></a>ReceiveArray deseni

ReceiveArray deseninde, istemci kodu bir dizi bildirir ve onu bellek ayıran ve onu başharfe alan bir yönteme geçirir. C++ giriş parametresi türü bir işaretçi-to-hat: `Array<T>^*`. Aşağıdaki örnek, JavaScript'te bir dizi nesnesinin nasıl bildirilen ve belleğe ayrılan, öğeleri başharfe alan ve JavaScript'e döndüren bir C++ işlevine nasıl geçirilir gösterilmektedir. JavaScript ayrılan diziyi bir geri dönüş değeri olarak değerlendirir, ancak C++ işlevi bunu bir çıkış parametresi olarak değerlendirir.

[!code-javascript[cx_arrays#102](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_3.js)]

Aşağıdaki parçacık C++ yöntemini uygulamanın iki yolunu gösterir:

[!code-cpp[cx_arrays#02](../cppcx/codesnippet/CPP/js-array/class1.cpp#02)]

## <a name="fill-arrays"></a>Dizileri doldurma

Arayanda bir dizi ayırmak ve onu callee'de başlatmaveya değiştirmek istediğinizde, '' kullanın. `WriteOnlyArray` Sonraki örnek, javascript kullanan ve onu `WriteOnlyArray` arayan bir C++ işlevininasıl uygulayacağımı gösterir.

[!code-javascript[cx_arrays#103](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_5.js)]

Aşağıdaki parçacık C++ yönteminin nasıl uygulanacağını gösterir:

[!code-cpp[cx_arrays#03](../cppcx/codesnippet/CPP/js-array/class1.cpp#03)]

## <a name="array-conversions"></a>Dizi dönüşümleri

Bu örnek, diğer koleksiyon türlerini oluşturmak için [bir Platformun](../cppcx/platform-array-class.md) nasıl kullanılacağını gösterir:

[!code-cpp[cx_arrays#05](../cppcx/codesnippet/CPP/js-array/class1.cpp#05)]

Sonraki örnek, Bir [Platform::Dizic](../cppcx/platform-array-class.md) stili diziden nasıl inşa edilir ve ortak bir yöntemden döndürülür.

[!code-cpp[cx_arrays#06](../cppcx/codesnippet/CPP/js-array/class1.cpp#06)]

## <a name="jagged-arrays"></a>Pürüzlü diziler

Windows Runtime türü sistemi pürüzlü diziler kavramını desteklemez `IVector<Platform::Array<T>>` ve bu nedenle ortak bir yöntemde iade değeri veya yöntem parametresi olarak kullanamazsınız. Pürüzlü bir dizi veya ABI genelinde diziler `IVector<IVector<T>^>`dizisi geçmek için.

## <a name="use-arrayreference-to-avoid-copying-data"></a>Veri kopyalamayı önlemek için ArrayReference'ı kullanma

Verilerin ABI genelinde bir Platforma aktarıldığı bazı [senaryolarda::Dizi](../cppcx/platform-array-class.md), ve sonuçta bu verileri verimlilik için C stili bir dizide işlemek istiyorsanız, ekstra kopyalama işlemini önlemek için [Platform::ArrayReference'ı](../cppcx/platform-arrayreference-class.md) kullanabilirsiniz. Bir Platformu geçtiğiniz [zaman::ArrayReference](../cppcx/platform-arrayreference-class.md) bir parametreye `Platform::Array`bağımsız `ArrayReference` değişken olarak , verileri doğrudan belirttiğiniz C stili diziye depolar. Kaynak verilerde `ArrayReference` kilit bulunmadığını unutmayın, bu nedenle arama tamamlanmadan önce bu veriler başka bir iş parçacığı nda değiştirilir veya silinirse, sonuçlar tanımsız kalır.

Aşağıdaki kod snippet bir [DataReader](/uwp/api/windows.storage.streams.datareader) işleminin sonuçlarını nasıl `Platform::Array` kopyalayabilirsiniz (olağan desen) `ArrayReference` ve ardından verileri doğrudan C stili bir diziye kopyalamak için nasıl değiştirilmeye yönelik olarak gösterir:

[!code-cpp[cx_arrays#07](../cppcx/codesnippet/CPP/js-array/class1.h#07)]

## <a name="avoid-exposing-an-array-as-a-property"></a>Diziyi özellik olarak açığa çıkarmaktan kaçının

Genel olarak, istemci kodu `Platform::Array` yalnızca tek bir öğeye erişmeye çalışırken bile tüm dizi döndürüldüğünden, ref sınıfında bir türe özellik olarak maruz kalmaktan kaçınmalısınız. Bir sıra kapsayıcısını genel ref sınıfında bir özellik olarak ortaya çıkarmanız gerektiğinde, [Windows::Foundation::IVector](/uwp/api/windows.foundation.collections.ivector-1) daha iyi bir seçimdir. Özel veya dahili API'lerde (meta verilere yayınlanmayan), [std:vektör](../standard-library/vector-class.md)gibi standart bir C++ kapsayıcısı kullanmayı düşünün.

## <a name="see-also"></a>Ayrıca bkz.

[Tür Sistemi](../cppcx/type-system-c-cx.md)<br/>
[C++/CX Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad Alanları Başvurusu](../cppcx/namespaces-reference-c-cx.md)
