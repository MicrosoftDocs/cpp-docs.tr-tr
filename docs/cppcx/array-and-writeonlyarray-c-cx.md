---
title: Dizi ve WriteOnlyArray (C++/CX)
ms.date: 01/22/2017
ms.assetid: ef7cc5f9-cae6-4636-8220-f789e5b6aea4
ms.openlocfilehash: fd616487bd3c11544f12e84a7dc64f41e63d501a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209422"
---
# <a name="array-and-writeonlyarray-ccx"></a>Dizi ve WriteOnlyArray (C++/CX)

Normal C stili diziler serbestçe kullanabilirsiniz veya [std::array](../standard-library/array-class-stl.md) içinde bir C++/CX program (ancak [std::vector](../standard-library/vector-class.md) genellikle daha iyi bir seçimdir), ancak meta verilerinde de yayımlanmaktadır herhangi API'SİNDE dönüştürmeniz gerekir bir C tarzı dizi ya için vektör bir [Platform::Array](../cppcx/platform-array-class.md) veya [Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md) nasıl kullanıldığını bağlı olarak tür. [Platform::Array](../cppcx/platform-array-class.md) türüdür kadar verimli ne kadar güçlü [std::vector](../standard-library/vector-class.md), genel bir kural olarak dizi işlemleri çok sayıda gerçekleştirir, iç kod kullanımını kaçınmalısınız. öğeleri.

Aşağıdaki dizi türleri arasında ABI geçirilebilir:

1. const Platform::Array ^

1. Platform::Array ^ *

1. Platform::WriteOnlyArray

1. dönüş değeri Platform::Array ^

Windows çalışma zamanı tarafından tanımlanan dizi desenleri üç tür uygulamak için bu dizi türleri kullanın.

PassArray çağıran bir dizi yönteme başarılı olduğunda kullanılır. C++ giriş parametre türü hatalı `const` [Platform::Array](../cppcx/platform-array-class.md)\<T >.

FillArray doldurmak bir yöntem için bir dizi çağırana başarılı olduğunda kullanılır. C++ giriş parametre türü hatalı [Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md)\<T >.

ReceiveArray çağıran yöntem ayıran bir dizi aldığında kullanılır. İçinde C++/CX dönüş değeri olarak bir dizi içinde dizi dönebilirsiniz ^ veya, bunu bir out parametresi dizi türü olarak dönebilirsiniz ^ *.

## <a name="passarray-pattern"></a>PassArray düzeni

Ne zaman istemci kodu başarılı bir diziye bir C++ yöntemi ile yöntem değiştirmez, yöntem dizi bir dizi sabit kabul eder. ^. Windows çalışma zamanı uygulama ikili arabiriminde (ABI) düzeyinde, bu bir PassArray bilinir. Sonraki örnek, ondan okuyan bir C++ işlev JavaScript dilinde ayrılan dizi geçirilecek gösterilmektedir.

[!code-javascript[cx_arrays#101](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_1.js)]

Aşağıdaki kod parçacığı C++ yöntemi gösterir:

[!code-cpp[cx_arrays#01](../cppcx/codesnippet/CPP/js-array/class1.cpp#01)]

## <a name="receivearray-pattern"></a>ReceiveArray düzeni

ReceiveArray deseninde, istemci kodu bir diziyi bildirir ve kendisi için bellek ayırır ve onu başlatan bir yönteme geçirir. İşaretçi-için-hat C++ giriş parametre türü hatalı: `Array<T>^*`. Aşağıdaki örnek, bir dizi nesnesinde JavaScript bildirmek ve belleği ayırır, öğeleri başlatır ve JavaScript için döndüren bir C++ işlevine geçirmek gösterilmektedir. JavaScript, dönüş değeri olarak ayrılan dizi davranır, ancak isteğe bağlı olarak C++ işlev out parametresi değerlendirir.

[!code-javascript[cx_arrays#102](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_3.js)]

Aşağıdaki kod parçacığı C++ yöntemi uygulamak için iki yolunu gösterir:

[!code-cpp[cx_arrays#02](../cppcx/codesnippet/CPP/js-array/class1.cpp#02)]

## <a name="fill-arrays"></a>Diziler doldurun

Arayan bir dizi ayırmak ve başlatması veya çağrılan, kullanım değiştirmek istediğinizde `WriteOnlyArray`. Sonraki örnekte kullanan C++ işlevinin nasıl uygulandığını gösteren `WriteOnlyArray` ve JavaScript'ten çağırın.

[!code-javascript[cx_arrays#103](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_5.js)]

Aşağıdaki kod parçacığı, C++ yöntemi uygulamak gösterilmektedir:

[!code-cpp[cx_arrays#03](../cppcx/codesnippet/CPP/js-array/class1.cpp#03)]

## <a name="array-conversions"></a>Dizi dönüştürmeleri

Bu örnek nasıl kullanılacağını gösterir. bir [Platform::Array](../cppcx/platform-array-class.md) diğer türlerdeki koleksiyonlar oluşturmak için:

[!code-cpp[cx_arrays#05](../cppcx/codesnippet/CPP/js-array/class1.cpp#05)]

Sonraki örnek nasıl oluşturulacağını gösterir. bir [Platform::Array](../cppcx/platform-array-class.md) C stili dizisi ve ortak bir yöntemi döndürür.

[!code-cpp[cx_arrays#06](../cppcx/codesnippet/CPP/js-array/class1.cpp#06)]

## <a name="jagged-arrays"></a>Basit diziler

Windows çalışma zamanı tür sistemi, düzensiz diziler kavramını desteklemiyor ve bu nedenle kullanamazsınız `IVector<Platform::Array<T>>` genel bir yöntem dönüş değeri veya yöntemin parametre olarak. Basit bir dizi veya sıralarının ABI arasında geçirmek için kullanmak `IVector<IVector<T>^>`.

## <a name="use-arrayreference-to-avoid-copying-data"></a>Veri kopyalama önlemek için ArrayReference kullanın

Burada veri geçirilen ABI arasında bazı senaryolarda bir [Platform::Array](../cppcx/platform-array-class.md)ve sonuçta bu verimlilik için bir C tarzı dizi verilerini işlemek istiyorsanız, kullanabileceğiniz [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) Ek kopyalama işlemi önlemek için. Gönderdiğinizde bir [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) bağımsız değişken alan bir parametre olarak bir `Platform::Array`, `ArrayReference` verilerin belirttiğiniz doğrudan bir C tarzı dizi içine depolar. Yalnızca unutmayın, `ArrayReference` kilit kaynak veri serileştirilmesini, verileri değiştiren veya çağrı tamamlanmadan önce başka bir iş parçacığında silindi, sonuçlar tanımsız olup olmayacağını.

Aşağıdaki kod parçacığı, sonuçları kopyalamak gösterilmiştir bir [DataReader](/uwp/api/Windows.Storage.Streams.DataReader) işlemi bir `Platform::Array` (normal desenin) ve ardından yerine nasıl `ArrayReference` verileri doğrudan C stili diziye kopyalamak için:

[!code-cpp[cx_arrays#07](../cppcx/codesnippet/CPP/js-array/class1.h#07)]

## <a name="avoid-exposing-an-array-as-a-property"></a>Bir dizi özellik olarak kullanıma sunma kaçının

Genel olarak kullanıma sunma kaçınmalısınız bir `Platform::Array` türü bir başvuru sınıfının bir özellik olarak bile istemci kodunu yalnızca tek bir öğeye erişmeye çalıştığı sırada tüm dizi döndürdüğünden. Sıralı kapsayıcı ortak başvuru sınıfı, bir özellik olarak kullanıma sunmak ihtiyaç duyduğunuzda [Windows::Foundation::IVector](/uwp/api/Windows.Foundation.Collections.IVector_T_) daha iyi bir seçimdir. (Bu meta verileri yayımlanmayan) API'leri, özel veya iç gibi standart bir C++ kapsayıcı kullanmayı düşünün [std::vector](../standard-library/vector-class.md).

## <a name="see-also"></a>Ayrıca bkz.

[Tür Sistemi](../cppcx/type-system-c-cx.md)<br/>
[Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad Alanları Başvurusu](../cppcx/namespaces-reference-c-cx.md)
