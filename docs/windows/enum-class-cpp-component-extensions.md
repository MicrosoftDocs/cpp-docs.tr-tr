---
title: "Enum sınıfı (C++ bileşen uzantıları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 8010fa8c-bad6-45b4-8214-b4db64d7ffe1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 876cab344f1177000f63740ca6c33bc1db1afefe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="enum-class--c-component-extensions"></a>enum sınıfı (C++ Bileşen Uzantıları)
Numaralandırmalar adlı adlandırılmış sabitler kümesinden oluşan bir kullanıcı tanımlı tür ad alanı kapsamında bir numaralandırma bildirir.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 **Açıklamalar**  
  
 C + +/ CX ve C + +/ CLI desteği `public enum class` ve `private enum class` standart C++ benzer olduğu `enum class` ancak erişilebilirlik belirleyici eklenmesi. Altında **/CLR**, C ++ 11 `enum class` türü izin verilir ancak gerçekten ISO enum türü ve değil C + istediğiniz emin olmak için tasarlanmıştır C4472 uyarı oluşturacak +/ CX ve C + +/ CLI türü. ISO standart C++ hakkında daha fazla bilgi için `enum` anahtar sözcüğü, bkz: [numaralandırmalar](../cpp/enumerations-cpp.md).  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 **Sözdizimi**  
  
```  
  
      access  
      enum class  
      enumeration-identifier  
      [:underlying-type] { enumerator-list } [var];  
accessenum structenumeration-identifier[:underlying-type] { enumerator-list } [var];  
```  
  
 **Parametreler**  
  
 *erişim*  
 Olabilir numaralandırması erişilebilirliğini `public` veya `private`.  
  
 *numaralandırma tanıtıcısı*  
 Numaralandırma adı.  
  
 *temel alınan türü*  
 (İsteğe bağlı) Numaralandırma temel türü.  
  
 (İsteğe bağlı. Windows çalışma zamanı modülü yalnızca) olabilen numaralandırma, temel alınan türü `bool`, `char`, `char16`, `int16`, `uint16`, `int`, `uint32`, `int64`, veya `uint64`.  
  
 *Numaralandırıcı listesi*  
 Numaralandırıcı adlarının virgülle ayrılmış listesi.  
  
 Ya da örtük olarak derleyici tarafından veya açıkça gösterimi tarafından tanımlanan bir sabit ifadesine her Numaralandırıcı değeri *Numaralandırıcı*`=`*sabit ifadesi*. Örtük olarak tanımlanmışsa, varsayılan olarak, ilk Numaralayıcı sıfır değerdir. Sonraki her örtük olarak tanımlanan Numaralandırıcı önceki Numaralandırıcı + 1 değerini değerdir.  
  
 *var*  
 (İsteğe bağlı) Bir değişken numaralandırma türünün adı.  
  
 **Açıklamalar**  
  
 Daha fazla bilgi ve örnekler için bkz: [numaralandırmaları](http://msdn.microsoft.com/%20library/windows/apps/hh755820.aspx).  
  
 Bir numaralandırıcı değeri tanımlar sabit ifadesine göre gösterilemezse derleyici hata iletilerini gösterdiği Not *arka plandaki türünü*.  Ancak, derleyici temel alınan türü için uygun olan bir değer için bir hata bildirmiyor. Örneğin:  
  
-   Varsa *arka plandaki türünü* sayısal ve bir numaralandırıcı türü için maksimum değeri belirten, sonraki örtük olarak tanımlanan enumeratoin değerini temsil edilemez.  
  
-   Varsa *arka plandaki türünü* olan `bool`, ve ikiden fazla numaralandırıcılar örtük olarak tanımlanmış, ilk iki gösterilemez sonra numaralandırıcılar.  
  
-   Varsa *arka plandaki türünü* olan `char16`ve numaralandırma değeri ile 0xDFFF 0xD800 aralıkları, değer temsil edilebilir. Ancak, bir yarı Unicode olabilmesinden dolayı mantıksal olarak yanlış değer çifti vekil ve yalıtım modunda görünmemelidir.  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı 
 **Sözdizimi**  
  
```  
  
      access  
      enum class  
      name [:type] { enumerator-list } var;  
accessenum structname [:type] { enumerator-list } var;  
```  
  
 **Parametreler**  
  
 `access`  
 Enum erişilebilirlik.  Ya da olabilir **ortak** veya `private`.  
  
 `enumerator-list`  
 Listedeki tanımlayıcıları (numaralandırıcılar) virgülle ayrılmış listesi.  
  
 `name`  
 Numaralandırma adı.  Anonim yönetilen numaralandırmalar izin verilmiyor.  
  
 `type`(isteğe bağlı)  
 Temel alınan türü *tanımlayıcıları*.  Bu, int, kısa veya uzun işaretli veya işaretsiz sürümleri gibi herhangi bir skaler türü olabilir.  `bool`veya `char` de izin verilir.  
  
 `var`(isteğe bağlı)  
 Bir değişken numaralandırma türünün adı.  
  
 **Açıklamalar**  
  
 **Enum sınıfı** ve **enum struct** eşdeğer bildirimlerinin.  
  
 Numaralandırmalar iki tür vardır: yönetilen veya C + +/ CX ve standart.  
  
 Yönetilen veya C + +/ CX enum şu şekilde tanımlanabilir  
  
```cpp  
public enum class day {sun, mon };  
```  
  
 ve anlam olarak eşdeğerdir:  
  
```cpp  
ref class day {  
public:  
   static const int sun = 0;  
   static const int mon = 1;  
};  
```  
  
 Standart bir enum şu şekilde tanımlanabilir:  
  
```cpp  
enum day2 { sun, mon };  
```  
  
 ve anlam olarak eşdeğerdir:  
  
```cpp  
static const int sun = 0;  
static const int mon = 1;  
```  
  
 Yönetilen Numaralandırıcı adları (*tanımlayıcıları*) burada numaralandırması tanımlanan; numaralandırıcılar yapılan tüm başvuruları tam kapsamı içine eklenen değil (*adı* `::` *tanımlayıcısı*).  Bu nedenle, anonim yönetilen enum tanımlayamazsınız.  
  
 Standart bir enum numaralandırıcıları kesinlikle kapsayan kapsam içine eklenmiş.  Diğer bir deyişle, derleyici çevreleyen kapsamdaki bir numaralandırıcı aynı ada sahip başka bir simge varsa, bir hata oluşturur.  
  
 Visual C++ 2002 ve Visual C++ 2003'te numaralandırıcıları zayıf (görünür çevreleyen kapsamdaki aynı ada sahip başka bir tanımlayıcı değilse) eklenmiş.  
  
 Standart C++ enum tanımlanmışsa (olmadan **sınıfı** veya `struct`), ile derleniyor **/CLR** yönetilen bir enum derlenecek numaralandırma neden olur.  Numaralandırma yönetilmeyen numaralandırma semantiği sürdürüyor.  Unutmayın, derleyici yerleştirir bir öznitelik `Microsoft::VisualC::NativeEnumAttribute`, hangi yerel enum olmasını enum bir programcı hedefini belirlemek için Visual C++ derleyicisi tanır.  Diğer derleyiciler yönetilen bir enum yalnızca standart enum görürsünüz.  
  
 / CLR ile derlenmiş adlandırılmış, standart bir enum yönetilen enum bütünleştirilmiş görünür ve diğer yönetilen derleyici tarafından kullanılabilecek.   Ancak, adlandırılmamış standart enum derlemeden herkese görünür olmaz.  
  
 Visual C++ 2002 ve Visual C++ 2003 ' türü bir işlev parametresi olarak kullanılan standart bir enum:  
  
```cpp  
// mcppv2_enum.cpp  
// compile with: /clr  
enum E { a, b };  
void f(E) {System::Console::WriteLine("hi");}  
  
int main() {  
   E myi = b;  
   f(myi);  
}  
```  
  
 MSIL aşağıdakileri işlev imzası için yayma:  
  
```  
void f(int32);  
```  
  
 Ancak, derleyici geçerli sürümleri standart enum [NativeEnumAttribute] ve MSIL aşağıdakileri işlev imzası için yönetilen bir liste olarak yayılır:  
  
```  
void f(E)  
```  
  
 Yerel numaralandırmalar hakkında daha fazla bilgi için bkz: [C++ numaralandırma bildirimleri](../cpp/enumerations-cpp.md).  
  
 CLR enum değerleri hakkında daha fazla bilgi için bkz:  
  
-   [Temel alınan bir numaralandırma türü](../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md)  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 desc  
  
```cpp  
// mcppv2_enum_2.cpp  
// compile with: /clr  
// managed enum  
public enum class m { a, b };  
  
// standard enum  
public enum n { c, d };  
  
// unnamed, standard enum  
public enum { e, f } o;  
  
int main()   
{  
   // consume managed enum  
   m mym = m::b;  
   System::Console::WriteLine("no automatic conversion to int: {0}", mym);  
   System::Console::WriteLine("convert to int: {0}", (int)mym);  
  
   // consume standard enum  
   n myn = d;  
   System::Console::WriteLine(myn);  
  
   // consume standard, unnamed enum  
   o = f;  
   System::Console::WriteLine(o);  
}   
```  
  
 **Output**  
  
```Output  
no automatic conversion to int: b  
  
convert to int: 1  
  
1  
  
1  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)