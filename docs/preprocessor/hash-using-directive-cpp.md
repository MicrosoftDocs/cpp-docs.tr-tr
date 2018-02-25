---
title: "#using yönergesi (C + +/ CLR) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a1c43acde6e4f755c6757fc933c80091ba05927c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="using-directive-cclr"></a>#using yönergesi (C + +/ CLR)
Meta verileri ile derlenen bir program aktarır [/CLR](../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#using file [as_friend]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `file`  
 Bir MSIL .dll, .exe, .netmodule veya .obj. Örneğin,  
  
 `#using <MyComponent.dll>`  
  
 as_friend  
 `file` içindeki tüm türlerin erişilebilir olduğunu belirtir.  Daha fazla bilgi için bkz: [arkadaş derlemeler (C++)](../dotnet/friend-assemblies-cpp.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `file`, yönetilen verileri ve yönetilen yapıları için içe aktardığınız bir Microsoft ara dili (MSIL) dosyası olabilir. Derleme bildirimi bir .dll dosyası içeriyorsa sonra bildiriminde başvurulan tüm .dll alınır ve oluşturduğunuz derleme listeleyecek *dosya* bir derleme başvurusu olarak meta veriler.  
  
 Varsa `file` bütünleştirilmiş içermiyor (varsa `file` bir modül) ve geçerli (derleme) uygulamada modülü tür bilgilerini kullanmak istiyorsanız değil, yalnızca modülü parçası olduğunu belirten seçeneğiniz vardır derleme; kullanın[/ASSEMBLYMODULE](../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md). Ardından modüldeki türler derlemeye başvuruda bulunan herhangi bir uygulama için kullanılabilir hale gelir.  
  
 Kullanmak için bir alternatif `#using` olan [/FU](../build/reference/fu-name-forced-hash-using-file.md) derleyici seçeneği.  
  
 .exe derlemeleri geçirilen `#using` derlenmelidir (Visual Basic veya Visual C#, örneğin) Visual Studio .NET derleyicileri birini kullanarak.  İle derlenen bir .exe derlemesinden meta verileri içeri aktarılmaya çalışılırken **/CLR** bir dosya yükleme özel durumuna neden.  
  
> [!NOTE]
>  `#using` ile başvurulan bir bileşen, derleme zamanında içe aktarılan dosyanın farklı bir sürümüyle çalıştırılabilir, bu da bir istemci uygulamasının beklenmedik sonuçlar vermesine neden olur.  
  
 Derleyicinin derlemede (modül değil) bir türü tanıması için, türü çözümlemeye zorlanması gerekir. Bunu türün bir örneğini tanımlayarak yapabilirsiniz. Derleyiciye ilişkin bir derlemede bulunan tür adlarını çözmek için başka yollar da vardır; örneğin, derleme içinde bulunan bir türden devralıyorsanız, daha sonra tür adı derleyici tarafından bilinecektir.  
  
 Kullanılan kaynak kodundan yerleşik meta verileri içe aktarırken [__declspec(thread)](../cpp/thread.md), iş parçacığı semantiğini meta verilerde kalıcı değildir. Örneğin, ile bildirilen bir değişken **__declspec(thread)**, .NET Framework ortak dil çalışma zamanı için yapı ve üzerinden içe aktarılan bir programda derlenmiş `#using`, artık **__declspec () iş parçacığı)** semantiği değişkeni üzerinde.  
  
 `#using` ile başvurulan bir dosyada içe aktarılan tüm türler (hem yönetilen hem yerel) kullanılabilir, ancak derleyici yerel türleri tanımlar olarak değil bildirimler olarak sayar.  
  
 mscorlib.dll ile derleme yapılırken otomatik olarak başvurulan **/CLR**.  
  
 LIBPATH ortam değişkeni; derleyici `#using` öğesine geçirilen dosya adlarını çözümlemeye çalışırken aranacak dizinleri belirtir.  
  
 Derleyici aşağıdaki yolda başvuruları arar:  
  
-   `#using` deyiminde belirtilen bir yol.  
  
-   Geçerli dizin.  
  
-   .NET Framework sistem dizini.  
  
-   Eklendi dizinleri [/AI](../build/reference/ai-specify-metadata-directories.md) derleyici seçeneği.  
  
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