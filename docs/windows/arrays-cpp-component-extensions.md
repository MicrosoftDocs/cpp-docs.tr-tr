---
title: Diziler (C++ bileşen uzantıları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- cli::array
- details::array
- lang::array
dev_langs:
- C++
helpviewer_keywords:
- array keyword [C++]
- declaring arrays, about declaring arrays
- arrays [C++], multidimensional
- multidimensional arrays
- arrays [C++]
ms.assetid: 49445812-d775-4db1-a231-869598dbb955
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 58ba6d598223e63f5b28adcaedad653ffc6f386a
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645574"
---
# <a name="arrays-c-component-extensions"></a>Dizeler (C++ Bileşen Uzantıları)
`Platform::Array<T>` Türü C + +/ CX, veya **dizi** anahtar sözcüğü C + +/ CLI, belirtilen tür ve ilk değer dizisi bildirir.  
  
## <a name="all-platforms"></a>Tüm Platformlar  
 Bildirimde kapanış açılı ayraç (>) sonra bir tanıtıcı nesnesi (^) değiştirici kullanarak dizi bildirilmesi gerekir.  
 Dizideki öğelerin sayısını türün bir parçası değil. Farklı boyutlarda bir dizi için bir dizi değişkeni başvurabilir.  
  
 Standart C++, farklı alt simge oluşturma işaretçi aritmetik işlemlerine ilişkin bir eşanlam değil ve yer değiştirebilirlik değil.  
  
 Diziler hakkında daha fazla bilgi için bkz:  
  
-   [Nasıl yapılır: C++/CLI Üzerinde Dizi Kullanma](../dotnet/how-to-use-arrays-in-cpp-cli.md)  
    
-   [Değişken Bağımsız Değişken Listeleri (...) (C++/CLI)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 Dizi üyeleri olan `Platform` ad alanı. Diziler, yalnızca bir boyutlu olabilir.  
  
### <a name="syntax"></a>Sözdizimi  
  
 Sözdiziminin ilk örnekte **yeni başvuru** bir dizi ayırmak için toplam anahtar sözcüğü. İkinci örnek, yerel bir diziyi bildirir.  
  
```cpp  
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = 
    ref new[Platform::]Array<initialization-type> [{initialization-list [,...]}]  
  
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = 
    {initialization-list [,...]}  
```  
  
 *niteleyiciler* [isteğe bağlı]  
 Bir veya daha fazla bu depolama sınıfı tanımlayıcıları: [değişebilir](../cpp/mutable-data-members-cpp.md), [geçici](../cpp/volatile-cpp.md), [const](../cpp/const-cpp.md), [extern](../cpp/using-extern-to-specify-linkage.md), [statik](../cpp/static-members-cpp.md).  
  
 *dizi türü*  
 Dizi değişkeni türü. Geçerli türler, Windows çalışma zamanı sınıflar ve temel türler, başvuru sınıfları ve yapıları, değer sınıfları ve yapıları ve yerel işaretçileri olan (`type*`).  
  
 *derece* [isteğe bağlı]  
 Dizinin boyut sayısı. 1 olmalıdır.  
  
 *tanımlayıcı*  
 Dizi değişkeni adı.  
  
 *başlatma türü*  
 Dizi başlatma değerlerin türü. Genellikle, *dizi türü* ve *başlatma türü* aynı türdedir. Türleri dönüştürme ise farklı olabilir ancak *başlatma türü* için *dizi türü*— Örneğin, varsa *başlatma türü* türetilmiş*dizi türü*.  
  
 *başlatma listesi* [isteğe bağlı]  
 Dizi öğelerine ön değer atamak süslü ayraçlar değerleri virgülle ayrılmış listesi. Örneğin, varsa *derece boyutlarının listesi* olan `(3)`, tek boyutlu bir dizi 3 öğe bildirir *başlatma listesi* olabilir `{1,2,3}`.  
  
### <a name="remarks"></a>Açıklamalar  
  
 Başvuru sayılan bir dizi içeren bir tür olup olmadığını derleme zamanında algılayabilir `__is_ref_array(type)`. Daha fazla bilgi için [tür özellikleri için derleyici desteği](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: `/ZW`  
  
### <a name="examples"></a>Örnekler  
 Aşağıdaki örnek, 100 öğeleri olan tek boyutlu dizi oluşturur.  
  
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
  
 Sözdiziminin ilk örnekte **gcnew** anahtar sözcüğü, bir dizi ayırmak için. İkinci örnek, yerel bir diziyi bildirir.  
  
```cpp  
[qualifiers] [cli::]array<[qualifiers] array-type [,rank]>^ identifier = 
    gcnew [cli::]array<initialization-type[,rank]>(rank-size-list[,...]) [{initialization-list [,...]}]  
  
[qualifiers] [cli::]array<[qualifiers] array-type [,rank]>^ identifier = 
    {initialization-list [,...]}  
```  
  
 *niteleyiciler* [isteğe bağlı]  
 Bir veya daha fazla bu depolama sınıfı tanımlayıcıları: [değişebilir](../cpp/mutable-data-members-cpp.md), [geçici](../cpp/volatile-cpp.md), [const](../cpp/const-cpp.md), [extern](../cpp/using-extern-to-specify-linkage.md), [statik](../cpp/static-members-cpp.md).  
  
 *dizi türü*  
 Dizi değişkeni türü. Geçerli türler Windows çalışma zamanı sınıflar ve temel türler, başvuru sınıfları ve yapıları, değer sınıfları ve yapıları, yerel işaretçiler (`type*`) ve yerel POD (düz eski veriler) türleri.  
  
 *derece* [isteğe bağlı]  
 Dizinin boyut sayısı. Varsayılan değer 1'dir; en fazla 32'dir. Dizinin her boyutunun kendisi bir dizidir.  
  
 *tanımlayıcı*  
 Dizi değişkeni adı.  
  
 *başlatma türü*  
 Dizi başlatma değerlerin türü. Genellikle, *dizi türü* ve *başlatma türü* aynı türdedir. Türleri dönüştürme ise farklı olabilir ancak *başlatma türü* için *dizi türü*— Örneğin, varsa *başlatma türü* türetilmiş*dizi türü*.  
  
 *derece boyutlarının listesi*  
 Dizideki her boyutun boyutu virgülle ayrılmış listesi. Alternatif olarak, *başlatma listesi* parametresi belirtildiğinde, derleyici her boyutu çıkarabilir ve *derece boyutlarının listesi* atlanabilir. 
  
 *başlatma listesi* [isteğe bağlı]  
 Dizi öğelerine ön değer atamak süslü ayraçlar değerleri virgülle ayrılmış listesi. Veya virgülle ayrılmış bir listesini iç içe geçmiş *başlatma listesi* başlatmak çok boyutlu bir dizideki öğeler öğeleri.  
  
 Örneğin, varsa *derece boyutlarının listesi* olan `(3)`, tek boyutlu bir dizi 3 öğe bildirir *başlatma listesi* olabilir `{1,2,3}`. Varsa *derece boyutlarının listesi* olan `(3,2,4)`, ilk boyutu, 2 öğe ikinci ve üçüncü 4 öğelerinde 3 öğelerin üç boyutlu bir diziyi bildirir *başlatma listesi* olabilir `{{1,2,3},{0,0},{-5,10,-21,99}}`.)  
  
### <a name="remarks"></a>Açıklamalar  
  
 **dizi** bulunduğu [Platform, varsayılan ve cli ad alanları](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md) ad alanı.  
  
 Standart C++ gibi bir dizi dizinleri sıfır tabanlıdır ve bir dizi köşeli ayraç ([]) kullanarak alt simgeli. Standart C++, çok boyutlu bir dizi dizinleri her boyut için köşeli ayraç ([]) işleçleri kümesini yerine her boyut için dizin listesinde belirtilir. Örneğin, *tanımlayıcı*[*index1*, *index2*] yerine *tanımlayıcı*[*index1*] [ *index2*].  
  
 Tüm yönetilen diziler devralınacak `System::Array`. Herhangi bir yöntemi veya özelliği `System::Array` dizi değişkenine doğrudan uygulanabilir.  
  
 Öğe türü bir dizi ayırmak zaman işaretçisidir-yönetilen bir sınıf için öğeleri 0 olarak başlatılır.  
  
 Bir değer türü olduğunda, öğe türü bir dizi ayırmak `V`, için varsayılan oluşturucu `V` her dizi öğesine uygulanır. Daha fazla bilgi için [C++ yerel türlerinin .NET Framework eşdeğerleri (C + +/ CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md).  
  
 Derleme zamanında bir türde bir ortak dil çalışma zamanı (CLR) diziyle olup algılayabilir `__is_ref_array(type)`. Daha fazla bilgi için [tür özellikleri için derleyici desteği](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: `/clr`  
  
### <a name="examples"></a>Örnekler  
 Aşağıdaki örnek, 100 öğeleri olan tek boyutlu bir dizi ve ilk boyutunun 3 öğe, 5 öğeleri ikinci ve üçüncü 6 öğe içeren üç boyutlu bir dizi oluşturur.  
  
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
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)