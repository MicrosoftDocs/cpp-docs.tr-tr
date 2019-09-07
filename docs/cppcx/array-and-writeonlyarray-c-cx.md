---
title: Array ve WriteOnlyArray (C++/CX)
ms.date: 01/22/2017
ms.assetid: ef7cc5f9-cae6-4636-8220-f789e5b6aea4
ms.openlocfilehash: 2ade7981d391288edd78f622b4753d546c5eaa04
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740684"
---
# <a name="array-and-writeonlyarray-ccx"></a>Array ve WriteOnlyArray (C++/CX)

Bir C++/CX programında normal C stili diziler veya [std:: Array](../standard-library/array-class-stl.md) kullanabilirsiniz ( [std:: vector](../standard-library/vector-class.md) genellikle daha iyi bir seçimdir), ancak meta verilerde yayınlanan herhangi bir API 'de, C stili bir diziyi veya vektörü [Platform:: Array öğesine dönüştürmeniz gerekir ](../cppcx/platform-array-class.md)veya [Platform:: WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md) , kullanılma şekline bağlı olarak yazın. [Platform:: Array](../cppcx/platform-array-class.md) türü etkin veya [std:: vector](../standard-library/vector-class.md)olarak güçlü değildir, bu nedenle genel bir kılavuz olarak dizi öğelerinde çok fazla işlem gerçekleştiren iç kodda kullanımını önlemelidir.

Aşağıdaki dizi türleri ABı arasında geçirilebilir:

1. const Platform:: Array ^

1. Platform:: Array ^ *

1. Platform:: WriteOnlyArray

1. Platform:: Array ^ değerini döndür

Bu dizi türlerini, Windows Çalışma Zamanı tarafından tanımlanan üç dizi deseni uygulamak için kullanırsınız.

Çağıran bir diziyi bir yönteme geçtiğinde kullanılan PassArray. C++ Giriş parametresi türü `const` [Platform:: Array](../cppcx/platform-array-class.md)\<T >.

FillArray, çağıran yöntem için bir dizi geçtiğinde kullanılır. C++ Giriş parametresi türü [Platform:: WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md)\<T >.

Çağıran yöntemin ayırdığı bir dizi aldığında kullanılan ReceiveArray. /CX C++içinde, dönüş değerindeki diziyi bir ^ dizisi olarak döndürebilir ya da bunu, dizi ^ * olan out parametresi olarak döndürebilirsiniz.

## <a name="passarray-pattern"></a>PassArray düzeni

İstemci kodu bir yöntemi bir C++ yönteme geçirdiğinde ve Yöntem onu değiştirmezse, yöntem diziyi bir const dizisi olarak kabul eder. Windows Çalışma Zamanı Application binary Interface (ABı) düzeyinde, bu, PassArray olarak bilinir. Sonraki örnek, JavaScript 'te ayrılan bir dizinin onu okuyan bir C++ işleve nasıl geçirileceğini gösterir.

[!code-javascript[cx_arrays#101](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_1.js)]

Aşağıdaki kod parçacığında C++ yöntemi gösterilmektedir:

[!code-cpp[cx_arrays#01](../cppcx/codesnippet/CPP/js-array/class1.cpp#01)]

## <a name="receivearray-pattern"></a>ReceiveArray düzeni

ReceiveArray modelinde, istemci kodu bir dizi bildirir ve onu kendisi için belleği ayıran ve Başlatan bir yönteme geçirir. C++ Giriş parametresi türü bir hat işaretçisi: `Array<T>^*`. Aşağıdaki örnek, JavaScript 'te bir dizi nesnesinin nasıl bildirilemeyeceğini ve bunu belleği ayıran, öğeleri başlatan C++ ve JavaScript 'e döndüren bir işleve iletmenin nasıl yapılacağını gösterir. JavaScript, ayrılan diziyi dönüş değeri olarak değerlendirir, ancak C++ işlev bunu bir out parametresi olarak değerlendirir.

[!code-javascript[cx_arrays#102](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_3.js)]

Aşağıdaki kod parçacığında C++ yöntemi uygulamak için iki yol gösterilmektedir:

[!code-cpp[cx_arrays#02](../cppcx/codesnippet/CPP/js-array/class1.cpp#02)]

## <a name="fill-arrays"></a>Dizileri doldur

Çağıranda bir dizi ayırmak ve aranan bölümünde başlatmak veya değiştirmek istediğinizde kullanın `WriteOnlyArray`. Sonraki örnek, tarafından kullanılan C++ `WriteOnlyArray` ve JavaScript 'ten çağıran bir işlevin nasıl uygulanacağını gösterir.

[!code-javascript[cx_arrays#103](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_5.js)]

Aşağıdaki kod parçacığında C++ yönteminin nasıl uygulanacağı gösterilmektedir:

[!code-cpp[cx_arrays#03](../cppcx/codesnippet/CPP/js-array/class1.cpp#03)]

## <a name="array-conversions"></a>Dizi dönüştürmeleri

Bu örnek, diğer koleksiyon türlerini oluşturmak için [Platform:: Array](../cppcx/platform-array-class.md) öğesinin nasıl kullanılacağını gösterir:

[!code-cpp[cx_arrays#05](../cppcx/codesnippet/CPP/js-array/class1.cpp#05)]

Sonraki örnekte, C stili dizisinden bir [Platform:: Array](../cppcx/platform-array-class.md) öğesinin nasıl oluşturulacağı ve bir ortak yöntemden nasıl döndürdüğü gösterilmektedir.

[!code-cpp[cx_arrays#06](../cppcx/codesnippet/CPP/js-array/class1.cpp#06)]

## <a name="jagged-arrays"></a>Sivri diziler

Windows çalışma zamanı tür sistemi, pürüzlü Diziler kavramını desteklemez ve bu nedenle bir ortak yöntemde dönüş değeri veya `IVector<Platform::Array<T>>` yöntem parametresi olarak kullanamazsınız. ABı arasında pürüzlü bir diziyi veya dizi dizilerini geçirmek için kullanın `IVector<IVector<T>^>`.

## <a name="use-arrayreference-to-avoid-copying-data"></a>Veri kopyalamayı önlemek için ArrayReference kullanın

Verilerin ABı arasında [Platform:: Array](../cppcx/platform-array-class.md)içine geçirildiği bazı senaryolarda ve son olarak bu verileri bir C stili dizide verimlilik için işlemek istiyorsanız, ek kopyalama işleminin oluşmaması için [Platform:: arrayreference](../cppcx/platform-arrayreference-class.md) kullanabilirsiniz. `ArrayReference` Bir `Platform::Array` [Platform:: arrayreference](../cppcx/platform-arrayreference-class.md) ' ı alan bir parametreye bağımsız değişken olarak geçirdiğinizde, verileri doğrudan belirttiğiniz bir C stili dizisine depolar. Kaynak verilerde kilit olmadığını `ArrayReference` unutmayın. bu nedenle, çağrı tamamlanmadan önce veriler başka bir iş parçacığında değiştirilir veya silinirse sonuçlar tanımsız olur.

Aşağıdaki kod parçacığı, bir [DataReader](/uwp/api/Windows.Storage.Streams.DataReader) işleminin sonuçlarının bir (normal bir `Platform::Array` düzende) nasıl kopyalanacağını ve sonra verileri doğrudan C stili bir diziye kopyalamak için nasıl yerine konacak `ArrayReference` olduğunu gösterir:

[!code-cpp[cx_arrays#07](../cppcx/codesnippet/CPP/js-array/class1.h#07)]

## <a name="avoid-exposing-an-array-as-a-property"></a>Bir diziyi özellik olarak açığa çıkarmaktan kaçının

Genellikle, istemci kodu yalnızca tek bir öğeye `Platform::Array` erişmeye çalıştığında bile tüm diziyi döndürüldüğünden, bir türü başvuru sınıfında özelliği olarak ortaya çıkarmaktan kaçınmanız gerekir. Bir dizi kapsayıcısını ortak bir başvuru sınıfında özellik olarak kullanıma sunmanıza gerek duyduğunuzda, [Windows:: Foundation:: IVector](/uwp/api/Windows.Foundation.Collections.IVector_T_) daha iyi bir seçimdir. Özel veya iç API 'lerde (meta verilerde yayımlanmayan), [std:: vector](../standard-library/vector-class.md)gibi standart C++ bir kapsayıcı kullanmayı düşünün.

## <a name="see-also"></a>Ayrıca bkz.

[Tür Sistemi](../cppcx/type-system-c-cx.md)<br/>
[C++/CX Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad Alanları Başvurusu](../cppcx/namespaces-reference-c-cx.md)
