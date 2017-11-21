---
title: "Diziler (C++ bileşen uzantıları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- cli::array
- details::array
- lang::array
dev_langs: C++
helpviewer_keywords:
- array keyword [C++]
- declaring arrays, about declaring arrays
- arrays [C++], multidimensional
- multidimensional arrays
- arrays [C++]
ms.assetid: 49445812-d775-4db1-a231-869598dbb955
caps.latest.revision: "34"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a2f0f4100344fbb2990e9feeb2b455642852c320
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="arrays-c-component-extensions"></a>Dizeler (C++ Bileşen Uzantıları)
`Platform::Array<T>` Türü C + +/ CX, veya `array` anahtar sözcüğü C + +/ CLI, belirtilen tür ve ilk değer bir dizi bildirir.  
  
## <a name="all-platforms"></a>Tüm Platformlar  
 Dizi bildiriminde kapanış açılı ayraç (>) sonra tanıtıcı nesnesi (^) değiştiricisi kullanılarak bildirilmelidir.  
 Dizideki öğeler sayısı türünün bir parçası değil. Farklı boyutlarda diziler için bir dizi değişkeni başvurabilir.  
  
 Standart C++ aksine alt simge oluşturma işaretçi aritmetiği eşanlamlısı değil ve yer değiştirebilme değil.  
  
 Dizileri hakkında daha fazla bilgi için bkz:  
  
-   [Nasıl yapılır: dizileri C + kullanma +/ CLI](../dotnet/how-to-use-arrays-in-cpp-cli.md)  
    
-   [Değişken bağımsız değişken listeleri (...) (C + +/ CLI)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 Diziler üyeleri olan `Platform` ad alanı. Diziler yalnızca tek boyutlu olabilir.  
  
### <a name="syntax"></a>Sözdizimi  
  
 İlk örnek sözdizimi kullanan `ref new` bir dizi ayırmak için toplam anahtar sözcüğü. İkinci örnek, yerel bir dizi bildirir.  
  
```  
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = 
    ref new[Platform::]Array<initialization-type> [{initialization-list [,...]}]  
  
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = 
    {initialization-list [,...]}  
```  
  
 *niteleyiciler* [isteğe bağlı]  
 Bir veya daha fazla bu depolama sınıfı tanımlayıcıları: [değişebilir](../cpp/mutable-data-members-cpp.md), [volatile](../cpp/volatile-cpp.md), [const](../cpp/const-cpp.md), [extern](../cpp/using-extern-to-specify-linkage.md), [statik](../cpp/static-members-cpp.md).  
  
 `array-type`  
 Dizi değişkeni türü. Geçerli türleridir Windows çalışma zamanı sınıfları ve temel türleri, ref sınıflar ve yapılar, değer sınıfları ve yapıları ve yerel işaretçileri (`type*`).  
  
 `rank`[isteğe bağlı]  
 Dizi boyutları sayısı. 1 olmalıdır.  
  
 `identifier`  
 Dizi değişkeni adı.  
  
 `initialization-type`  
 Dizi başlatma değerlerin türü. Genellikle, `array-type` ve `initialization-type` aynı türde olan. Türleri dönüştürme ise farklı olabilir ancak `initialization-type` için `array-type`— Örneğin, varsa `initialization-type` türetildiği `array-type`.  
  
 `initialization-list`[isteğe bağlı]  
 Dizideki öğeler başlatma süslü ayraç değerleri virgülle ayrılmış listesi. Örneğin, varsa `rank-size-list` olan `(3)`, tek boyutlu dizi 3 öğelerinin bildirir `initialization list` olabilir `{1,2,3}`.  
  
### <a name="remarks"></a>Açıklamalar  
  
 Başvuruları sayılan bir diziyle türü olup olmadığını derleme zamanında algılayabilir `__is_ref_array(type)`. Daha fazla bilgi için bkz: [tür özellikleri için derleyici desteği](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
### <a name="examples"></a>Örnekler  
 Aşağıdaki örnek, 100 öğesi içeren bir tek boyutlu dizi oluşturur.  
  
```cpp  
// cwr_array.cpp  
// compile with: /ZW  
using namespace Platform;  
ref class MyClass {};  
int main() {  
   // one-dimensional array  
   Array<MyClass^>^ My1DArray = ref new Array<MyClass^>(100);  
   My1DArray[99] = ref new MyClass();  
}  
```  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı 
  
### <a name="syntax"></a>Sözdizimi  
  
 Sözdizimi ilk örneği kullanan `gcnew` anahtar sözcüğü bir dizi ayrılamadı. İkinci örnek, yerel bir dizi bildirir.  
  
```  
[qualifiers] [cli::]array<[qualifiers] array-type [,rank]>^ identifier = 
    gcnew [cli::]array<initialization-type[,rank]>(rank-size-list[,...]) [{initialization-list [,...]}]  
  
[qualifiers] [cli::]array<[qualifiers] array-type [,rank]>^ identifier = 
    {initialization-list [,...]}  
```  
  
 *niteleyiciler* [isteğe bağlı]  
 Bir veya daha fazla bu depolama sınıfı tanımlayıcıları: [değişebilir](../cpp/mutable-data-members-cpp.md), [volatile](../cpp/volatile-cpp.md), [const](../cpp/const-cpp.md), [extern](../cpp/using-extern-to-specify-linkage.md), [statik](../cpp/static-members-cpp.md).  
  
 `array-type`  
 Dizi değişkeni türü. Geçerli türleridir Windows çalışma zamanı sınıfları ve temel türleri, ref sınıflar ve yapılar, değer sınıflar ve yapılar, yerel işaretçileri (`type*`) ve yerel POD (düz eski verileri) türleri.  
  
 `rank`[isteğe bağlı]  
 Dizi boyutları sayısı. Varsayılan değer 1'dir; en fazla 32'dir. Dizinin her boyut kendisini bir dizidir.  
  
 `identifier`  
 Dizi değişkeni adı.  
  
 `initialization-type`  
 Dizi başlatma değerlerin türü. Genellikle, `array-type` ve `initialization-type` aynı türde olan. Türleri dönüştürme ise farklı olabilir ancak `initialization-type` için `array-type`— Örneğin, varsa `initialization-type` türetildiği `array-type`.  
  
 `rank-size-list`  
 Dizideki her boyut boyutunu virgülle ayrılmış listesi. Alternatif olarak, varsa `initialization-list` parametresi belirtilirse, derleyicinin her boyut boyutunu türetme ve `rank-size-list` atlanabilir. 
  
 `initialization-list`[isteğe bağlı]  
 Dizideki öğeler başlatma süslü ayraç değerleri virgülle ayrılmış listesi. Veya virgülle ayrılmış bir listesini iç içe geçmiş *başlatma listesi* çok boyutlu bir dizi öğeleri başlatma öğeleri.  
  
 Örneğin, varsa `rank-size-list` olan `(3)`, tek boyutlu dizi 3 öğelerinin bildirir `initialization list` olabilir `{1,2,3}`. Eğer `rank-size-list` olan `(3,2,4)`, ilk boyutu, 2 öğeleri ikinci ve üçüncü 4 öğelerinde 3 öğe üç boyutlu bir dizi bildirir `initialization-list` olabilir `{{1,2,3},{0,0},{-5,10,-21,99}}`.)  
  
### <a name="remarks"></a>Açıklamalar  
  
 `array`içinde [Platform, varsayılan ve cli ad alanları](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md) ad alanı.  
  
 Standart C++ gibi bir dizi dizinlerini sıfır tabanlı ve bir dizi köşeli ayraç ([]) kullanarak alt indisli bir dizi. Standart C++, çok boyutlu bir dizi dizinlerini köşeli ayraç ([]) işleçleri her boyut için bir dizi yerine her boyut için dizinler listesinde belirtilir. Örneğin, *tanımlayıcısı*[*dizin1*, *dizin2*] yerine *tanımlayıcısı*[*dizin1*] [ *dizin2*].  
  
 Tüm yönetilen diziler devralınmalıdır `System::Array`. Herhangi bir yöntemi veya özelliği `System::Array` doğrudan dizi değişkeni uygulanabilir.  
  
 Ne zaman, öğe türü bir dizi tahsis işaretçidir-yönetilen bir sınıfa 0 başlatılmış öğeleridir.  
  
 Bir değer türü değil, öğe türü bir dizi tahsis ne zaman `V`, varsayılan oluşturucusu `V` her bir dizi öğesine uygulanır. Daha fazla bilgi için bkz: [C++ yerel türlerinin .NET Framework eşdeğerleri (C + +/ CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md).  
  
 Derleme zamanında bir türü bir ortak dil çalışma zamanı (CLR) diziyle olup olmadığını algılayabilir `__is_ref_array(type)`. Daha fazla bilgi için bkz: [tür özellikleri için derleyici desteği](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
### <a name="examples"></a>Örnekler  
 Aşağıdaki örnek, 100 öğesi içeren bir tek boyutlu dizi ve 3 öğelerindeki ilk boyut, 5 öğelerini ikinci ve üçüncü 6 öğelerini içeren üç boyutlu bir dizi oluşturur.  
  
```cpp  
// clr_array.cpp  
// compile with: /clr  
ref class MyClass {};  
int main() {  
   // one-dimensional array  
   array<MyClass ^> ^ My1DArray = gcnew array<MyClass ^>(100);  
   My1DArray[99] = gcnew MyClass();  
  
   // three-dimensional array  
   array<MyClass ^, 3> ^ My3DArray = gcnew array<MyClass ^, 3>(3, 5, 6);  
   My3DArray[0,0,0] = gcnew MyClass();  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma zamanı platformları için bileşen uzantıları](../windows/component-extensions-for-runtime-platforms.md)