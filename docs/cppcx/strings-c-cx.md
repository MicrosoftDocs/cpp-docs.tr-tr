---
title: Dizeler (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 5b34e1df-7c2b-4269-aba8-b767d36c49d9
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8f5c5e4cfe13f72585a2566773c88724f3618784
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33092476"
---
# <a name="strings-ccx"></a>Dizeler (C + +/ CX)
Windows çalışma zamanı metinde temsil edilir C + +/ CX tarafından [Platform::String sınıfı](../cppcx/platform-string-class.md). Kullanım `Platform::String Class` dizeleri geri ve İleri Windows çalışma zamanı sınıflarının yöntemleri için geçirdiğiniz veya uygulama ikili arabirimi (ABI) sınırından diğer Windows çalışma zamanı bileşenleri ile etkileşim kurarken. `Platform::String Class` Tam özellikli string sınıfı olacak şekilde tasarlanmamış birkaç ortak dize işlemleri, ancak onun için yöntemleri sağlar. C++ modülünüzün standart C++ dize türleri gibi kullandığınız [wstring](../standard-library/basic-string-class.md) tüm önemli metin işleme ve son sonucu için sonra dönüştürme için [Platform::String ^](../cppcx/platform-string-class.md) ortak bir bilgisayardan veya geçirmeden önce arabirim. Kolay ve verimli arasında dönüştürme yapma `wstring` veya `wchar_t*` ve `Platform::String`.  
  
 **Hızlı geçişi**  
  
 Bazı durumlarda, güvenli bir şekilde gerçekleştirebilmesi derleyici doğrulayabilirsiniz bir `Platform::String` veya geçirmek bir `String` temel dize veri kopyalama olmadan bir işlev. Bu tür işlemler olarak da bilinir *hızlı geçişi* ve şeffaf bir şekilde gerçekleşir.  
  
## <a name="string-construction"></a>Dize oluşturma  
 Değeri bir `String` nesnesidir bir değişmez (salt okunur) dizisi `char16` (16 bit Unicode) karakter. Çünkü bir `String` nesnesidir değişmez, yeni bir dize sabit değeri için atamasının bir `String` değişkenini gerçekte özgün değiştirir `String` yeni bir nesne `String` nesne. Birleştirme işlemleri içerir özgün yok etme `String` nesne ve yeni bir nesne oluşturma.  
  
 **Değişmez Değerler**  
  
 A *karakterinden* tek tırnak işaretleri içine bir karakter ve bir *değişmez değer dize* çift tırnak içine alınmış bir karakter sırasıdır. Bir dize başlatmak için bir hazır değer kullanırsanız ^ değişken, derleyici varsayar değişmez değeri, oluşur `char16` karakter. Diğer bir deyişle, sabit 'L' dizesi değiştirici ile koyun veya sabit listesinde değişmez alın yok bir **_T()** veya **TEXT()** makrosu. Unicode C++ desteği hakkında daha fazla bilgi için bkz: [Unicode Programlama Özeti](../text/unicode-programming-summary.md).  
  
 Aşağıdaki örnek oluşturmak için çeşitli yollar gösterir `String` nesneleri.  
  
 [!code-cpp[cx_strings#01](../cppcx/codesnippet/CPP/cppcx_strings/class1.cpp#01)]  
  
## <a name="string-handling-operations"></a>Dize işlemleri işleme  
 `String` Sınıfı yöntemleri ve sağlar işleçleri birleştirme için dizeler ve diğer temel dize işlemleri karşılaştırma. Daha kapsamlı dize işlemeleri gerçekleştirme için kullanmak `String::Data()` değerini almak için üye işlevini `String^` nesnesinin bir `const wchar_t*`. Başlatmak için bu değeri kullanın bir `std::wstring`, işleme işlevlerini zengin dize sağlar.  
  
 [!code-cpp[cx_strings#03](../cppcx/codesnippet/CPP/cppcx_strings/class1.cpp#03)]  
  
## <a name="string-conversions"></a>Dize dönüştürme  
 A `Platform::String` yalnızca içerebilir `char16` karakter veya `NULL` karakter. 8 bit karakter ile çalışmak uygulamanız varsa, kullanmak [String::Data](../cppcx/platform-string-class.md#data) metin olarak ayıklamak için bir `const wchar_t*`. Daha sonra uygun Windows işlevleri kullanabilirsiniz veya veriler üzerinde işlem yaparsınız ve dönüştürmek için standart kitaplık işlevlerini yeniden bir `wchar_t*` veya [wstring](../standard-library/basic-string-class.md), yeni bir oluşturmak için kullanabileceğiniz `Platform::String`.  
  
 Aşağıdaki kod parçası, dönüştürmek gösterilmiştir bir `String^` gelen ve giden değişken bir `wstring` değişkeni. Bu örnekte kullanılan dize düzenlemesi hakkında daha fazla bilgi için bkz: [basic_string::replace](../standard-library/basic-string-class.md#replace).  
  
 [!code-cpp[cx_strings#04](../cppcx/codesnippet/CPP/cppcx_strings/class1.cpp#04)]  
  
## <a name="string-length-and-embedded-null-values"></a>Dize uzunluğu ve katıştırılmış NULL değerler  
 [String::Length](../cppcx/platform-string-class.md#length) bayt sayısını değil dizesinde karakterlerin sayısını döndürür. Bir dizesi oluşturmak için yığın anlamları kullandığınızda onu açıkça belirtmediğiniz sürece sonlandırma NULL karakteri sayılmaz.  
  
 A `Platform::String` ancak NULL bir birleştirme işleminin sonucu olduğunda yalnızca katıştırılmış NULL değerler içerebilir. Katıştırılmış null dize değişmez değerleri içinde desteklenmez; Katıştırılmış null değerlere bu şekilde başlatmak için bu nedenle, kullanamazsınız bir `Platform::String`. NULL değerler katıştırılmış bir `Platform::String` için atandığında dize, örneğin, görüntülendiğinde göz ardı edilir bir `TextBlock::Text` özelliği. Katıştırılmış null dize değeri döndürdüğünde kaldırılır `Data` özelliği.  
  
## <a name="stringreference"></a>StringReference  
 Bazı durumlarda, bir std::wstring, veya wchar_t dize ya da L kodunuzu (a) alır"" dize sabit değeri ve yalnızca geçirir, bir dize alır başka bir yöntem açın ^ giriş parametresi olarak. Özgün dize arabellek kendisini geçerli kalır ve işlev döndürülmeden önce değiştirmediğini sürece dönüştürebilirsiniz `wchar_t*` veya dize değişmez değer için bir [Platform::StringReference](../cppcx/platform-stringreference-class.md)ve, yerinegeçirin`Platform::String^`. Bu olduğundan izin `StringReference` kullanıcı tanımlı bir dönüştürme sahip `Platform::String^`. Kullanarak `StringReference` bir kopyasının dize verilerini yapmaktan kaçınabilirsiniz. Burada, geçirme dizeler veya çok sayıda çok büyük dizeleri geçirilirken Döngülerde, büyük olasılıkla bir önemli performans iyileştirme kullanarak elde edebilirsiniz `StringReference`. Ancak çünkü `StringReference` temelde özgün dize arabelleğine taşır bellek bozulmasını önlemek için çok dikkatli kullanmanız gerekir. Değil geçirmelisiniz bir `StringReference` zaman uyumsuz bir yöntem için özgün dizeye bu yöntem döndürüldüğünde kapsamında olması garanti sürece. Bir dize ^ gelen başlatılmış ikinci bir atama işlem oluşursa bir StringReference bir ayırma ve dize verilerin kopyasını zorlar. Bu durumda, performans avantajı kaybedersiniz `StringReference`.  
  
 Unutmayın `StringReference` standart bir C++ sınıf türü bir başvuru sınıf tanımladığınız ref sınıfları ortak arabiriminde kullanamazsınız.  
  
 Aşağıdaki örnek StringReference kullanmayı gösterir:  
  
```  
void GetDecodedStrings(std::vector<std::wstring> strings)  
{  
    using namespace Windows::Security::Cryptography;  
    using namespace Windows::Storage::Streams;  
  
    for (auto&& s : strings)  
    {  
        // Method signature is IBuffer^ CryptographicBuffer::DecodeFromBase64String (Platform::String^)  
        // Call using StringReference:  
        IBuffer^ buffer = CryptographicBuffer::DecodeFromBase64String(StringReference(s.c_str()));  
  
        //...do something with buffer  
    }  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerleşik türler](http://msdn.microsoft.com/en-us/acc196fd-09da-4882-b554-6c94685ec75f)