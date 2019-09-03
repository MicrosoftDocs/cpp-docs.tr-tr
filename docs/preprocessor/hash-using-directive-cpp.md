---
title: '#using yönergesi (C++/CLI)'
ms.date: 08/29/2019
f1_keywords:
- friend_as_cpp
- '#using'
- friend_as
- '#using_cpp'
helpviewer_keywords:
- using directive (#using)
- '#using directive'
- LIBPATH environment variable
- preprocessor, directives
ms.assetid: 870b15e5-f361-40a8-ba1c-c57d75c8809a
ms.openlocfilehash: 5dae5c277055157aef5451c19ee020fbbd2aaccb
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220203"
---
# <a name="using-directive-ccli"></a>#using yönergesi (C++/CLI)

Meta verileri [/clr](../build/reference/clr-common-language-runtime-compilation.md)ile derlenen bir programa içeri aktarır.

## <a name="syntax"></a>Sözdizimi

> **#using** *Dosya* [**as_friend**]

### <a name="parameters"></a>Parametreler

*dosyasýný*\
Bir MSIL .dll, .exe, .netmodule veya .obj. Örneğin,

`#using <MyComponent.dll>`

**as_friend**\
*Dosyadaki* tüm türlerin erişilebilir olduğunu belirtir. Daha fazla bilgi için bkz. [arkadaş derlemelerC++()](../dotnet/friend-assemblies-cpp.md).

## <a name="remarks"></a>Açıklamalar

*Dosya* , yönetilen veriler ve yönetilen yapılar için içeri aktardığınız bir Microsoft ara DILI (MSIL) dosyası olabilir. Bir. dll dosyası bir derleme bildirimi içeriyorsa, bildirimde başvurulan tüm. dll 'ler içeri aktarılır ve oluşturmakta olduğunuz derleme, meta verilerde *dosyayı* bir derleme başvurusu olarak listeler.

*Dosya* bir derleme içermiyorsa ( *Dosya* bir modüldür) ve geçerli (derleme) uygulamasındaki modülden tür bilgilerini kullanmayı düşünmüyorsanız, yalnızca modülün derlemeyi parçası olduğunu belirten seçeneğiniz vardır. [/ASSEMBLYMODULE](../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)kullanın. Ardından modüldeki türler derlemeye başvuruda bulunan herhangi bir uygulama için kullanılabilir hale gelir.

**#Using** kullanımına alternatif olarak [/Fu](../build/reference/fu-name-forced-hash-using-file.md) derleyici seçeneği vardır.

**#using** geçirilen. exe derlemeleri .NET Visual Studio derleyicilerinin (örneğin Visual Basic veya görseden C#biri) kullanılarak derlenmelidir.  `/clr` ile derlenmiş .exe derlemesinden meta veriler içe aktarmaya çalışıldığında dosya yükleme özel durumu oluşur.

> [!NOTE]
> **#Using** başvurulan bir bileşen, derleme zamanında içeri aktarılan dosyanın farklı bir sürümüyle çalıştırılabilir, böylece bir istemci uygulaması beklenmedik sonuçlara neden olur.

Derleyicinin bir derlemede (modül değil) bir türü tanımasını sağlamak için, türün çözümlenmesinin zorunlu olması gerekir. Örneğin, türü bir örnek tanımlayarak bu uygulamayı zorlayabilirsiniz. Derleyici için bir derlemede tür adlarını çözümlemek için başka yollar vardır. Örneğin, derlemedeki bir türden devralma durumunda tür adı derleyici tarafından bilinir.

[__Declspec (thread)](../cpp/thread.md)kullanan kaynak kodundan oluşturulan meta verileri içeri aktarırken, iş parçacığı semantiği meta verilerde kalıcı olmaz. Örneğin, .NET Framework ortak dil çalışma zamanı için oluşturulmuş bir programda derlenen ve sonra **#using**ile içeri aktarılan **__declspec (thread)** ile belirtilen bir değişken, değişkende **__declspec (thread)** semantiklerine sahip olmayacaktır.

**#Using** tarafından başvurulan bir dosyada içeri aktarılan tüm türler (hem yönetilen hem de yerel) kullanılabilir, ancak derleyici yerel türleri tanımlar değil bildirim olarak değerlendirir.

`/clr` ile derlerken, mscorlib.dll'ye otomatik olarak başvurulur.

LıBPATH ortam değişkeni, derleyicinin **#using**iletilen dosya adlarını çözümlediğinde arama yapılacak dizinleri belirtir.

Derleyici, aşağıdaki yol boyunca başvuruları arar:

- **#Using** bildiriminde belirtilen bir yol.

- Geçerli dizin.

- .NET Framework sistem dizini.

- [/AI](../build/reference/ai-specify-metadata-directories.md) derleyici seçeneğiyle eklenen dizinler.

- LIBPATH ortam değişkenindeki dizinler.

## <a name="example"></a>Örnek

Bir derleme (C) derleyebilir ve kendisine başka bir derlemeye (A) başvuruda bulunan bir derlemeye (B) başvuru yaptıysanız, C 'deki türlerinden birini açıkça kullanmadığınız durumlar dışında açıkça derlemeye başvuru yapmak zorunda kalmazsınız.

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

Aşağıdaki örnekte, *using_assembly_A. dll*dosyasına başvurulmayan bir derleyici hatası yoktur, çünkü program *using_assembly_A. cpp*içinde tanımlı türlerden hiçbirini kullanmaz.

```cpp
// using_assembly_C.cpp
// compile with: /clr
#using "using_assembly_B.dll"
int main() {
   B b;
   b.Test();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md)
