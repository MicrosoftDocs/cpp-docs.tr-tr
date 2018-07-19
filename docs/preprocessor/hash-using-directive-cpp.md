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
ms.openlocfilehash: c2255f5de9cc26505bb07110da6368a039009c6c
ms.sourcegitcommit: b8b1cba85ff423142d73c888be26baa8c33f3cdc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39093039"
---
# <a name="using-directive-ccli"></a>#using yönergesi (C + +/ CLI)
İle derlenmiş bir programa meta veri aktarır [/CLR](../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#using file [as_friend]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `file`  
 Bir MSIL .dll, .exe, .netmodule veya .obj. Örneğin,  
  
 `#using <MyComponent.dll>`  
  
 as_friend  
 `file` içindeki tüm türlerin erişilebilir olduğunu belirtir.  Daha fazla bilgi için [arkadaş derlemeler (C++)](../dotnet/friend-assemblies-cpp.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `file`, yönetilen verileri ve yönetilen yapıları için içe aktardığınız bir Microsoft ara dili (MSIL) dosyası olabilir. Bir .dll dosyası bir derleme bildirimi içeren sonra bildiriminde atıf yapılan tüm .dll aktarılır ve oluşturuyor olduğunuz derleme listeler *dosya* bir bütünleştirilmiş kod başvurusu olarak meta.  
  
 Varsa `file` derleme içermiyor (varsa `file` bir modüldür) ve modülü tür bilgilerini geçerli (derleme) kullanmak istiyorsanız değil, yalnızca modülün parçası olduğunu gösteren seçeneğiniz vardır derleme; kullanın[Assemblymodule](../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md). Ardından modüldeki türler derlemeye başvuruda bulunan herhangi bir uygulama için kullanılabilir hale gelir.  
  
 Kullanılacak alternatif `#using` olduğu [/FU](../build/reference/fu-name-forced-hash-using-file.md) derleyici seçeneği.  
  
 geçirilen .exe derlemeleri `#using` derlenmelidir .NET Visual Studio derleyicileri (Visual Basic veya Visual C#, örneğin) birini kullanarak.  İle derlenmiş .exe derlemesinden meta veriler içe aktarmaya çalışıldığında **/CLR** bir dosya yükleme özel neden olur.  
  
> [!NOTE]
>  `#using` ile başvurulan bir bileşen, derleme zamanında içe aktarılan dosyanın farklı bir sürümüyle çalıştırılabilir, bu da bir istemci uygulamasının beklenmedik sonuçlar vermesine neden olur.  
  
 Derleyicinin derlemede (modül değil) bir türü tanıması için, türü çözümlemeye zorlanması gerekir. Bunu türün bir örneğini tanımlayarak yapabilirsiniz. Derleyiciye ilişkin bir derlemede bulunan tür adlarını çözmek için başka yollar da vardır; örneğin, derleme içinde bulunan bir türden devralıyorsanız, daha sonra tür adı derleyici tarafından bilinecektir.  
  
 Kullanılan kaynak kodundan oluşturulan meta veri aktarırken [gt;__declspec(thread)](../cpp/thread.md), iş parçacığı semantiği meta veri içinde kalıcı yapılmaz. Örneğin, bildirilen bir değişken **gt;__declspec(thread)**, .NET Framework ortak dil çalışma zamanı için derleme ve ile içe aktarılan bir programda derlenmiş `#using`, artık **__declspec () iş parçacığı)** semantiği.  
  
 `#using` ile başvurulan bir dosyada içe aktarılan tüm türler (hem yönetilen hem yerel) kullanılabilir, ancak derleyici yerel türleri tanımlar olarak değil bildirimler olarak sayar.  
  
 mscorlib.dll ile derleme yaparken otomatik olarak başvurulan **/CLR**.  
  
 LIBPATH ortam değişkeni; derleyici `#using` öğesine geçirilen dosya adlarını çözümlemeye çalışırken aranacak dizinleri belirtir.  
  
 Derleyici aşağıdaki yolda başvuruları arar:  
  
-   `#using` deyiminde belirtilen bir yol.  
  
-   Geçerli dizin.  
  
-   .NET Framework sistem dizini.  
  
-   Eklenen dizinler [/AI](../build/reference/ai-specify-metadata-directories.md) derleyici seçeneği.  
  
-   LIBPATH ortam değişkenindeki dizinler.  
  
## <a name="example"></a>Örnek  
 Bir derleme (C) oluşturursanız ve başka bir derlemeye (A) başvuru yapan bir derlemeye (B) başvuruda bulunursanız, A'nın türlerinden birini C'de açıkça kullanmadığınız sürece A derlemesine açıkça başvuruda bulunmanız gerekmez.  
  
```  
// using_assembly_A.cpp  
// compile with: /clr /LD  
public ref class A {};  
```  
  
## <a name="example"></a>Örnek  
  
```  
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
  
```  
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
