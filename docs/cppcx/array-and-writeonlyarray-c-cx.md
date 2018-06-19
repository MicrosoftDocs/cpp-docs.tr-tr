---
title: Dizi ve WriteOnlyArray (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: ef7cc5f9-cae6-4636-8220-f789e5b6aea4
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 47c26ef4058cc3116d964740a93f7395c300b92b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089398"
---
# <a name="array-and-writeonlyarray-ccx"></a>Dizi ve WriteOnlyArray (C + +/ CX)
Normal C tarzı diziler serbestçe kullanabilirsiniz veya [std::array](../standard-library/array-class-stl.md) C + +/ CX programı (rağmen [std::vector](../standard-library/vector-class.md) genellikle daha iyi bir seçimdir), ancak meta verilerinde yayımlanır herhangi bir API'yi içinde bir C tarzı dizi dönüştürmeniz gerekir veya için vektör bir [Platform::Array](../cppcx/platform-array-class.md) veya [Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md) nasıl kullanıldığını bağlı olarak türü. [Platform::Array](../cppcx/platform-array-class.md) türüdür ne kadar etkili ne kadar güçlü [std::vector](../standard-library/vector-class.md), genel bir kılavuz olarak dizi işlemlerinin çok gerçekleştirir iç kod kullanımını kaçınmalısınız. öğeleri.  
  
 Aşağıdaki dizi türleri arasında ABI geçirilebilir:  
  
1.  const Platform::Array ^  
  
2.  Platform::Array ^ *  
  
3.  Platform::WriteOnlyArray  
  
4.  Platform::Array değerini döndürmek ^  
  
 Windows çalışma zamanı tarafından tanımlanan bir dizi desenleri üç tür uygulamak için bu dizi türlerini kullanın.  
  
 PassArray  
 Çağıran bir dizi için bir yöntem başarılı olduğunda kullanılır. C++ giriş parametresi türü `const` [Platform::Array](../cppcx/platform-array-class.md)\<T >.  
  
 FillArray  
 Arayan doldurmak yöntemi için bir dizi başarılı olduğunda kullanılır. C++ giriş parametresi türü [Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md)\<T >.  
  
 ReceiveArray  
 Arayan yöntemi ayıran bir dizi aldığında kullanılır. C + +/ CX dönüş değeri olarak bir dizi dizi dönebilirsiniz ^ veya, onu bir out parametresi olarak dizi yazarken dönebilirsiniz ^ *.  
  
## <a name="passarray-pattern"></a>PassArray deseni  
 İstemci kodu C++ yöntemi için bir dizi geçirir ve yöntemi değiştirmez, yöntem dizi const dizi kabul eder. ^. Windows çalışma zamanı uygulama ikili arabirimi (ABI) düzeyinde bu PassArray bilinir. Sonraki örnek nasıl JavaScript'te ondan okuyan bir C++ işlevi için ayrılmış bir dizi iletileceğini gösterir.  
  
 [!code-javascript[cx_arrays#101](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_1.js)]  
  
 Aşağıdaki kod parçacığında C++ yöntemini gösterir:  
  
 [!code-cpp[cx_arrays#01](../cppcx/codesnippet/CPP/js-array/class1.cpp#01)]  
  
## <a name="receivearray-pattern"></a>ReceiveArray deseni  
 ReceiveArray düzeninde istemci kodu bir dizi bildirir ve bunun için bellek ayırır ve onu başlatır bir yönteme geçirir. C++ giriş parametresi türü ise işaretçi-için-hat: `Array<T>^*`. Aşağıdaki örnek, bir dizi nesnesi JavaScript'te bildirin ve bellek ayırır, öğeleri başlatır ve JavaScript için döndüren bir C++ işlevine geçirin gösterilmektedir. JavaScript ayrılmış dizi dönüş değeri olarak değerlendirir, ancak isteğe bağlı olarak C++ işlevi out parametresi değerlendirir.  
  
 [!code-javascript[cx_arrays#102](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_3.js)]  
  
 Aşağıdaki kod parçacığında C++ yöntemi uygulamak için iki yol gösterir:  
  
 [!code-cpp[cx_arrays#02](../cppcx/codesnippet/CPP/js-array/class1.cpp#02)]  
  
## <a name="fill-arrays"></a>Diziler doldurun  
 Çağıran bir dizide ayırmak ve başlatılamadı veya Aranan, kullanım değiştirmek istediğinizde `WriteOnlyArray`. Sonraki örnek kullanan bir C++ işlevinin nasıl uygulandığını gösterir `WriteOnlyArray` ve JavaScript'ten çağırın.  
  
 [!code-javascript[cx_arrays#103](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_5.js)]  
  
 Aşağıdaki kod parçacığında C++ yöntemi gösterilmektedir:  
  
 [!code-cpp[cx_arrays#03](../cppcx/codesnippet/CPP/js-array/class1.cpp#03)]  
  
## <a name="array-conversions"></a>Dizi dönüştürmeleri  
 Bu örnek nasıl kullanılacağını gösteren bir [Platform::Array](../cppcx/platform-array-class.md) koleksiyonları diğer türleri oluşturmak için:  
  
 [!code-cpp[cx_arrays#05](../cppcx/codesnippet/CPP/js-array/class1.cpp#05)]  
  
 Sonraki örnek nasıl oluşturulacağını gösteren bir [Platform::Array](../cppcx/platform-array-class.md) ' nden bir C stil dizi ve ortak yönteminden döndürün.  
  
 [!code-cpp[cx_arrays#06](../cppcx/codesnippet/CPP/js-array/class1.cpp#06)]  
  
## <a name="jagged-arrays"></a>Basit diziler  
 Windows çalışma zamanı tür sistemi basit diziler kavramını desteklemez ve bu nedenle kullanamazsınız `IVector<Platform::Array<T>>` genel yöntem dönüş değeri veya yöntem parametresi olarak. Basit bir dizi veya bir dizi sıraları ABI arasında geçirmek için kullanmak `IVector<IVector<T>^>`.  
  
## <a name="use-arrayreference-to-avoid-copying-data"></a>Veri kopyalama önlemek için ArrayReference kullanın  
 Burada veri geçirilen ABI arasında bazı senaryolarda bir [Platform::Array](../cppcx/platform-array-class.md)ve sonuçta bir C tarzı dizisi verimliliği için bu verileri işlemek istiyorsanız, kullanabileceğiniz [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) Ek kopyalama işlemi önlemek için. Geçirdiğiniz zaman bir [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) geçen bir parametre bağımsız değişkeni olarak bir `Platform::Array`, `ArrayReference` belirttiğiniz doğrudan bir C tarzı diziye verileri depolar. Yalnızca unutmayın, `ArrayReference` kilit bu nedenle kaynak verilere sahip, verileri değiştiren veya çağrı tamamlanmadan önce başka bir iş parçacığında silinmiş sonuçları tanımsız olup olmayacağını.  
  
 Aşağıdaki kod parçacığını sonuçlarını kopyalama gösterilmektedir bir [DataReader](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.datareader.aspx) işlemi içine bir `Platform::Array` (normal düzeni) ve ardından yerine nasıl `ArrayReference` verileri doğrudan C tarzı dizisine kopyalamak için:  
  
 [!code-cpp[cx_arrays#07](../cppcx/codesnippet/CPP/js-array/class1.h#07)]  
  
## <a name="avoid-exposing-an-array-as-a-property"></a>Bir özellik olarak bir dizi gösterme kaçının  
 Genel olarak, gösterme kaçınmalısınız bir `Platform::Array` yazın ref sınıf özelliği olarak bile istemci kodu yalnızca tek bir öğe erişmeye çalıştığı sırada tüm diziyi döndürdüğünden. Sıralı kapsayıcı bir ortak ref sınıf özelliği olarak kullanıma sunmak gerektiğinde [Windows::Foundation::IVector](http://msdn.microsoft.com/library/windows/apps/br206631.aspx) daha iyi bir seçimdir. Özel veya dahili (meta verileri yayımlanmayan) API'leri, göz önünde bulundurun gibi standart bir C++ kapsayıcı kullanılarak [std::vector](../standard-library/vector-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür sistemi](../cppcx/type-system-c-cx.md)   
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)   
 [Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)