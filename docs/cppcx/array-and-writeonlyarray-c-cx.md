---
title: Dizi ve WriteOnlyArray (C++/CX)
ms.date: 01/22/2017
ms.assetid: ef7cc5f9-cae6-4636-8220-f789e5b6aea4
ms.openlocfilehash: 1980fbcd1e2fa8cdaa48e00d2e7de9e45ac96a92
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231032"
---
# <a name="array-and-writeonlyarray-ccx"></a>Dizi ve WriteOnlyArray (C++/CX)

Normal C stili dizileri veya [`std::array`](../standard-library/array-class-stl.md) bir C++/CX programında ( [`std::vector`](../standard-library/vector-class.md) genellikle daha iyi bir seçimdir) ücretsiz olarak kullanabilirsiniz, ancak meta verilerde yayınlanan HERHANGI bir API 'de, bir C stili diziyi veya vektörü, [`Platform::Array`](../cppcx/platform-array-class.md) [`Platform::WriteOnlyArray`](../cppcx/platform-writeonlyarray-class.md) nasıl kullanıldığına bağlı olarak bir veya türüne dönüştürmeniz gerekir. [`Platform::Array`](../cppcx/platform-array-class.md)Tür, ne kadar verimli ya da güçlü değildir [`std::vector`](../standard-library/vector-class.md) , bu nedenle genel bir kılavuz olarak dizi öğelerinde çok fazla işlem gerçekleştiren iç kodda kullanımını önlemelidir.

Aşağıdaki dizi türleri ABı arasında geçirilebilir:

1. `const Platform::Array^`

1. `Platform::Array^*`

1. `Platform::WriteOnlyArray`

1. dönüş değeri`Platform::Array^`

Bu dizi türlerini, Windows Çalışma Zamanı tarafından tanımlanan üç dizi deseni uygulamak için kullanırsınız.

PassArray \
Çağıran bir diziyi bir yönteme geçtiğinde kullanılır. C++ giriş parametresi türü **`const`** [`Platform::Array`](../cppcx/platform-array-class.md) \<T> .

FillArray\
Çağıran, metodu için bir dizi geçtiğinde kullanılır. C++ giriş parametresi türü [`Platform::WriteOnlyArray`](../cppcx/platform-writeonlyarray-class.md) \<T> .

ReceiveArray \
Çağıran yöntemin ayırdığı bir dizi aldığında kullanılır. C++/CX ' te dönüş değerindeki diziyi bir ^ dizisi olarak döndürebilir ya da bunu bir out parametresi olarak ^ * türü olarak döndürebilirsiniz.

## <a name="passarray-pattern"></a>PassArray düzeni

İstemci kodu bir diziyi C++ yöntemine geçtiğinde ve Yöntem onu değiştirmezse, yöntem diziyi bir olarak kabul eder `const Array^` . Windows Çalışma Zamanı Application binary Interface (ABı) düzeyinde, bu, *Passarray*olarak bilinir. Sonraki örnek, JavaScript 'te ayrılmış bir dizinin bir C++ işlevine nasıl geçirileceğini gösterir.

[!code-javascript[cx_arrays#101](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_1.js)]

Aşağıdaki kod parçacığında C++ yöntemi gösterilmektedir:

[!code-cpp[cx_arrays#01](../cppcx/codesnippet/CPP/js-array/class1.cpp#01)]

## <a name="receivearray-pattern"></a>ReceiveArray düzeni

*Receivearray* modelinde, istemci kodu bir dizi bildirir ve onu kendisi için belleği ayıran ve Başlatan bir yönteme geçirir. C++ giriş parametresi türü, hat işaretçisi: `Array<T>^*` . Aşağıdaki örnek, JavaScript 'te bir dizi nesnesinin nasıl bildirilemeyeceğini ve bunu belleği ayıran, öğeleri Başlatan C++ işlevine nasıl geçireceğiniz ve JavaScript 'e döndürdüğünü gösterir. JavaScript, ayrılan diziyi bir dönüş değeri olarak değerlendirir, ancak C++ işlevi bunu bir out parametresi olarak değerlendirir.

[!code-javascript[cx_arrays#102](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_3.js)]

Aşağıdaki kod parçacığında, C++ yöntemini uygulamak için iki yol gösterilmektedir:

[!code-cpp[cx_arrays#02](../cppcx/codesnippet/CPP/js-array/class1.cpp#02)]

## <a name="fill-arrays"></a>Dizileri doldur

Çağıranda bir dizi ayırmak ve aranan bölümünde başlatmak veya değiştirmek istediğinizde kullanın `WriteOnlyArray` . Sonraki örnek, JavaScript 'ten tarafından kullanılan ve çağıran bir C++ işlevinin nasıl uygulanacağını gösterir `WriteOnlyArray` .

[!code-javascript[cx_arrays#103](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_5.js)]

Aşağıdaki kod parçacığında C++ yönteminin nasıl uygulanacağı gösterilmektedir:

[!code-cpp[cx_arrays#03](../cppcx/codesnippet/CPP/js-array/class1.cpp#03)]

## <a name="array-conversions"></a>Dizi dönüştürmeleri

Bu örnek [`Platform::Array`](../cppcx/platform-array-class.md) , diğer koleksiyon türlerini oluşturmak için öğesinin nasıl kullanılacağını gösterir:

[!code-cpp[cx_arrays#05](../cppcx/codesnippet/CPP/js-array/class1.cpp#05)]

Sonraki örnekte, bir [`Platform::Array`](../cppcx/platform-array-class.md) C stili dizisinden nasıl oluşturulduğu ve bir ortak yöntemden nasıl döndürdüğü gösterilmektedir.

[!code-cpp[cx_arrays#06](../cppcx/codesnippet/CPP/js-array/class1.cpp#06)]

## <a name="jagged-arrays"></a>Sivri diziler

Windows Çalışma Zamanı tür sistemi, pürüzlü Diziler kavramını desteklemez ve bu nedenle bir `IVector<Platform::Array<T>>` ortak yöntemde dönüş değeri veya yöntem parametresi olarak kullanamazsınız. ABı arasında pürüzlü bir diziyi veya dizi dizilerini geçirmek için kullanın `IVector<IVector<T>^>` .

## <a name="use-arrayreference-to-avoid-copying-data"></a>Veri kopyalamayı önlemek için ArrayReference kullanın

Verilerin ABı arasında geçirildiği bazı senaryolarda [`Platform::Array`](../cppcx/platform-array-class.md) ve sonunda bu verileri verimlilik Için C stili bir dizide işlemek istiyorsanız, ek kopyalama işleminin oluşmaması Için [Platform:: arrayreference](../cppcx/platform-arrayreference-class.md) kullanabilirsiniz. ' A sahip bir [`Platform::ArrayReference`](../cppcx/platform-arrayreference-class.md) parametreye bir bağımsız değişken olarak geçirdiğinizde, `Platform::Array` `ArrayReference` verileri doğrudan belirttiğiniz bir C stili dizisine depolayacaktır. `ArrayReference`Kaynak verilerde kilit olmadığını unutmayın. bu nedenle, çağrı tamamlanmadan önce veriler başka bir iş parçacığında değiştirilir veya silinirse sonuçlar tanımsız olur.

Aşağıdaki kod parçacığı, bir [`DataReader`](/uwp/api/windows.storage.streams.datareader) işlemin sonuçlarının bir `Platform::Array` (normal düzende) nasıl kopyalanacağını ve sonra `ArrayReference` verileri doğrudan C stili bir diziye kopyalamak için nasıl yerine konacak olduğunu gösterir:

[!code-cpp[cx_arrays#07](../cppcx/codesnippet/CPP/js-array/class1.h#07)]

## <a name="avoid-exposing-an-array-as-a-property"></a>Bir diziyi özellik olarak açığa çıkarmaktan kaçının

Genellikle, `Platform::Array` istemci kodu yalnızca tek bir öğeye erişmeye çalıştığında bile tüm diziyi döndürüldüğünden, bir türü başvuru sınıfında özelliği olarak ortaya çıkarmaktan kaçınmanız gerekir. Bir dizi kapsayıcısını ortak bir başvuru sınıfında özellik olarak kullanıma sunmanıza gerek duyduğunuzda, [`Windows::Foundation::IVector`](/uwp/api/windows.foundation.collections.ivector-1) daha iyi bir seçimdir. Özel veya iç API 'lerde (meta verilerde yayımlanmayan), gibi standart bir C++ kapsayıcısı kullanmayı düşünün [`std::vector`](../standard-library/vector-class.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Tür sistemi](../cppcx/type-system-c-cx.md)<br/>
[C++/CX dil başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad alanı başvurusu](../cppcx/namespaces-reference-c-cx.md)
