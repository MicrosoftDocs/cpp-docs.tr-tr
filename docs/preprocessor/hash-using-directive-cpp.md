---
title: '#using yönergesi (C + +/ CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- friend_as_cpp
- '#using'
- friend_as
- '#using_cpp'
dev_langs:
- C++
helpviewer_keywords:
- using directive (#using)
- '#using directive'
- LIBPATH environment variable
- preprocessor, directives
ms.assetid: 870b15e5-f361-40a8-ba1c-c57d75c8809a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8a43946100146def9c0082f533c3657d7ab8ebac
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42466160"
---
# <a name="using-directive-ccli"></a>#using yönergesi (C + +/ CLI)
İle derlenmiş bir programa meta veri aktarır [/CLR](../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#using file [as_friend]  
```  
  
### <a name="parameters"></a>Parametreler  
*Dosya*  
Bir MSIL .dll, .exe, .netmodule veya .obj. Örneğin,  
  
`#using <MyComponent.dll>`  
  
*as_friend*  
İçindeki tüm türlerin olduğunu belirtir *dosya* erişilebilir. Daha fazla bilgi için [arkadaş derlemeler (C++)](../dotnet/friend-assemblies-cpp.md).  
  
## <a name="remarks"></a>Açıklamalar  
 
*Dosya* , yönetilen verileri ve yönetilen yapıları için içe aktardığınız bir Microsoft Ara dil (MSIL) dosyası olabilir. Bir .dll dosyası bir derleme bildirimi içeren sonra bildiriminde atıf yapılan tüm .dll aktarılır ve oluşturuyor olduğunuz derleme listeler *dosya* bir bütünleştirilmiş kod başvurusu olarak meta.  
  
Varsa *dosya* derleme içermiyor (varsa *dosya* bir modül) ve modülü tür bilgilerini geçerli (derleme) kullanmak istiyorsanız değil, yalnızca gösteren seçeneğiniz vardır Modülü bütünleştirilmiş kod parçasıdır; kullanma [assemblymodule](../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md). Ardından modüldeki türler derlemeye başvuruda bulunan herhangi bir uygulama için kullanılabilir hale gelir.  
  
Kullanılacak alternatif **#using** olduğu [/FU](../build/reference/fu-name-forced-hash-using-file.md) derleyici seçeneği.  
  
geçirilen .exe derlemeleri **#using** derlenmelidir .NET Visual Studio derleyicileri (Visual Basic veya Visual C#, örneğin) birini kullanarak.  `/clr` ile derlenmiş .exe derlemesinden meta veriler içe aktarmaya çalışıldığında dosya yükleme özel durumu oluşur.  
  
> [!NOTE]
> İle başvurulan bir bileşen **#using** neden beklenmedik sonuçlar için bir istemci uygulaması derleme zamanında içe aktarılan dosyanın farklı bir sürümüyle çalıştırılabilir.  
  
Derleyicinin derlemede (modül değil) bir türü tanıması için, türü çözümlemeye zorlanması gerekir. Bunu türün bir örneğini tanımlayarak yapabilirsiniz. Derleyiciye ilişkin bir derlemede bulunan tür adlarını çözmek için başka yollar da vardır; örneğin, derleme içinde bulunan bir türden devralıyorsanız, daha sonra tür adı derleyici tarafından bilinecektir.  
  
Kullanılan kaynak kodundan oluşturulan meta veri aktarırken [gt;__declspec(thread)](../cpp/thread.md), iş parçacığı semantiği meta veri içinde kalıcı yapılmaz. Örneğin, bildirilen bir değişken **gt;__declspec(thread)**, .NET Framework ortak dil çalışma zamanı için derleme ve ile içe aktarılan bir programda derlenmiş **#using**, artıkyoktur**gt;__declspec(thread)** semantiği.  
  
İçe aktarılan tüm türler (yönetilen ve yerel) tarafından başvurulan bir dosyada **#using** kullanılabilir, ancak derleyicinin tanımları değil bildirimler olarak yerel türler değerlendirir.  
  
`/clr` ile derlerken, mscorlib.dll'ye otomatik olarak başvurulur.  
  
LIBPATH ortam değişkeni derleyici geçirilen dosya adlarını çözümlemeye çalışırken aranacak dizinleri belirtir **#using**.  
  
Derleyici aşağıdaki yolda başvuruları arar:  
  
- Belirtilen bir yol **#using** deyimi.  
  
- Geçerli dizin.  
  
- .NET Framework sistem dizini.  
  
- Eklenen dizinler [/AI](../build/reference/ai-specify-metadata-directories.md) derleyici seçeneği.  
  
- LIBPATH ortam değişkenindeki dizinler.  
  
## <a name="example"></a>Örnek  
 
Bir derleme (C) oluşturursanız ve başka bir derlemeye (A) başvuru yapan bir derlemeye (B) başvuruda bulunursanız, A'nın türlerinden birini C'de açıkça kullanmadığınız sürece A derlemesine açıkça başvuruda bulunmanız gerekmez.  
  
```cpp  
// using_assembly_A.cpp  
// compile with: /clr /LD  
public ref class A {};  
```  
  
## <a name="example"></a>Örnek  
  
```cpp  
// using_assembly_B.cpp  
// compile with: /clr /LD  
#using "using_assembly_A.dll"  
public ref class B {  
public:  
   void Test(A a) {}  
   void Test() {}  
};    
```  
  
## <a name="example"></a>Örnek  
 
Aşağıdaki örnekte, using_assembly_A.dll öğesine başvuru yapılmadığı için oluşan bir derleyici hatası yoktur, çünkü program using_assembly_A.cpp içinde tanımlanmış türlerden birini kullanmamaktadır.  
  
```cpp  
// using_assembly_C.cpp  
// compile with: /clr  
#using "using_assembly_B.dll"  
int main() {  
   B b;  
   b.Test();  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz. 

[Ön işlemci Yönergeleri](../preprocessor/preprocessor-directives.md)