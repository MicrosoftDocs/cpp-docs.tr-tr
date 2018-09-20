---
title: . XML dosyasını işleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- XML documentation, processing XML file
ms.assetid: e70fdeae-80ac-4872-ab24-771c5635cfbf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f7cdbbe704e283177e4e3b4f0767db66e2e284e5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446328"
---
# <a name="xml-file-processing"></a>.Xml Dosyası İşleme

Derleyici, kodunuzda belgeleri oluşturmak için etiketli her yapı için bir kimlik dizesi oluşturur. Daha fazla bilgi için [önerilen etiketler belge açıklamaları](../ide/recommended-tags-for-documentation-comments-visual-cpp.md). Kimlik dizesi yapısını benzersiz olarak tanımlar. .Xml dosyası işleme programları kimliği dizesi belgeleri uygulandığı karşılık gelen .NET Framework meta verileri veya yansıma öğeyi tanımlamak için kullanabilirsiniz.

.Xml dosyası kodunuzu hiyerarşik bir gösterimini değil, her öğe için oluşturulan bir Kimliğe sahip düz bir liste.

Kimlik dizeleri oluşturduğunda, derleyici aşağıdaki kurallar gözlemler:

- Hiçbir boşluk dizesinde yerleştirilir.

- Kimlik dizesi ilk bölümünü izleyen iki nokta ile tek bir karakter ile tanımlanmakta üye türünü tanımlar. Aşağıdaki üye türleri kullanılır:

   |Karakter|Açıklama|
   |---------------|-----------------|
   |N|ad alanı<br /><br /> Belge açıklamaları için bir ad alanı ekleyemezsiniz, bir ad alanı başvurularını cref mümkündür.|
   |T|Tür: sınıf, arabirim, yapı, enum, temsilci|
   |D|typedef|
   |F|alan|
   |P|özellik (dizin oluşturucular veya diğer dizin oluşturulmuş özellikleri dahil)|
   |M|(tür özel yöntemler olarak Oluşturucular, işleçler ve diğerleri dahil) yöntemi|
   |E|olay|
   |!|Hata dizesi<br /><br /> Dizenin geri kalanı, hata hakkında bilgi sağlar. Visual C++ derleyicisi, çözümlenemeyen bağlantılar için hata bilgisi oluşturur.|

- İkinci dize ad alanı kökünde başlangıç öğesi tam olarak nitelenmiş adını parçasıdır. Öğe, kapsayan türü veya türleri ve ad alanı adı noktalarla ayrılmış. Öğenin adını nokta varsa, karma-işaretiyle ('#')'ya değiştirilir. Öğe adını doğrudan bir karma işareti olduğunu kabul edilir. Örneğin, tam olarak nitelenmiş adını `String` Oluşturucu "System.String.#ctor" olacaktır.

- Yöntemi için bağımsız değişken varsa özellikleri ve yöntemleri, parantez içindeki bağımsız değişken listesini takip eder. Hiçbir bağımsız değişken varsa, hiçbir parantez yok. Bağımsız değişkenlerin virgülle ayrılır. Her bağımsız değişken kodlama, doğrudan bir .NET Framework imzada nasıl kodlandığını izler:

   - Temel türler. Normal türleri (ELEMENT_TYPE_CLASS veya ELEMENT_TYPE_VALUETYPE), türün tam adı temsil edilir.

   - İç türleri (örneğin, ELEMENT_TYPE_I4 ELEMENT_TYPE_OBJECT, ELEMENT_TYPE_STRING, ELEMENT_TYPE_TYPEDBYREF. ve ELEMENT_TYPE_VOID) karşılık gelen tam tür adı tam olarak temsil edilir Örneğin, **System.Int32** veya **System.TypedReference**.

   - ELEMENT_TYPE_PTR olarak temsil edilir bir ' *' aşağıdaki değiştirilen türü.

   - ELEMENT_TYPE_BYREF olarak temsil edilir bir '\@' aşağıdaki değiştirilen türü.

   - ELEMENT_TYPE_PINNED olarak temsil edilir bir ' ^' aşağıdaki değiştirilen türü. Visual C++ derleyicisi, hiçbir zaman bu oluşturur.

   - ELEMENT_TYPE_CMOD_REQ olarak temsil edilir bir '&#124;' ve değiştirilen türü aşağıdaki değiştiricisi sınıfının tam adı. Visual C++ derleyicisi, hiçbir zaman bu oluşturur.

   - ELEMENT_TYPE_CMOD_OPT olarak temsil edilir bir '!' ve değiştirilen türü aşağıdaki değiştiricisi sınıfının tam adı.

   - ELEMENT_TYPE_SZARRAY "dizinin öğe türü aşağıdaki []" temsil edilir.

   - "[?]" ELEMENT_TYPE_GENERICARRAY temsil edilen aşağıdaki dizinin öğe türü. Visual C++ derleyicisi, hiçbir zaman bu oluşturur.

   - ELEMENT_TYPE_ARRAY olarak temsil edilir [*lowerbound*:`size`,*lowerbound*:`size`] Burada virgül sayısını ise boyut - 1 ve alt sınırı boyutunu ve her boyut bilinen ondalık biçimde temsil edilir. Alt sınır veya boyutu belirtilmezse, yalnızca atlanır. Belirli bir boyut için boyut ve alt sınır atlanırsa, ':' de atlanır. Örneğin, belirtilmeyen boyutları ve alt sınırı 1 ile 2 boyutlu bir dizi olan [1:, 1:].

   - ELEMENT_TYPE_FNPTR olarak temsil edilir "FUNC =:`type`(*imza*)", burada `type` dönüş türü ve *imza* yöntem bağımsız değişkenleri olan. Hiçbir bağımsız değişken varsa, parantezler göz ardı edilir. Visual C++ derleyicisi, hiçbir zaman bu oluşturur.

   Ayırt edici aşırı yüklenmiş yöntemler için hiçbir zaman kullanılmaz, çünkü aşağıdaki imza bileşenleri temsil edilmez:

   - Çağırma kuralı

   - Dönüş türü

   - ELEMENT_TYPE_SENTINEL

- Yalnızca dönüştürme işleçleri için yöntemin dönüş değeri olarak kodlanmış bir ' ~' gibi önceden kodlanmış dönüş türü tarafından izlenen.

- Genel türler için türü adını geri işaret ve ardından genel tür parametre sayısını belirten bir sayı tarafından izlenir.  Örneğin,

    ```xml
    <member name="T:MyClass`2">
    ```

   Olarak tanımlanan bir tür için `public class MyClass<T, U>`.

   Genel türler parametre olarak alan yöntemleri için genel tür parametreleri ile geri ticks başında sayı olarak belirtilen (örneğin \`0 \`1).  Her bir sayının temsil eden bir türün genel parametreleri için sıfır tabanlı bir dizi gösterimi.

## <a name="example"></a>Örnek

Aşağıdaki örnekler nasıl kimliği için bir sınıf dizeleri ve üyelerinin oluşturulması.

```cpp
// xml_id_strings.cpp
// compile with: /clr /doc /LD
///
namespace N {
// "N:N"

   /// <see cref="System" />
   //  <see cref="N:System"/>
   ref class X {
   // "T:N.X"

   protected:
      ///
      !X(){}
      // "M:N.X.Finalize", destructor's representation in metadata

   public:
      ///
      X() {}
      // "M:N.X.#ctor"

      ///
      static X() {}
      // "M:N.X.#cctor"

      ///
      X(int i) {}
      // "M:N.X.#ctor(System.Int32)"

      ///
      ~X() {}
      // "M:N.X.Dispose", Dispose function representation in metadata

      ///
      System::String^ q;
      // "F:N.X.q"

      ///
      double PI;
      // "F:N.X.PI"

      ///
      int f() { return 1; }
      // "M:N.X.f"

      ///
      int bb(System::String ^ s, int % y, void * z) { return 1; }
      // "M:N.X.bb(System.String,System.Int32@,System.Void*)"

      ///
      int gg(array<short> ^ array1, array< int, 2 >^ IntArray) { return 0; }
      // "M:N.X.gg(System.Int16[], System.Int32[0:,0:])"

      ///
      static X^ operator+(X^ x, X^ xx) { return x; }
     // "M:N.X.op_Addition(N.X,N.X)"

      ///
      property int prop;
      // "M:N.X.prop"

      ///
      property int prop2 {
      // "P:N.X.prop2"

         ///
         int get() { return 0; }
         // M:N.X.get_prop2

         ///
         void set(int i) {}
         // M:N.X.set_prop2(System.Int32)
      }

      ///
      delegate void D(int i);
      // "T:N.X.D"

      ///
      event D ^ d;
      // "E:N.X.d"

      ///
      ref class Nested {};
      // "T:N.X.Nested"

      ///
      static explicit operator System::Int32 (X x) { return 1; }
      // "M:N.X.op_Explicit(N.X!System.Runtime.CompilerServices.IsByValue)~System.Int32"
   };
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[XML Belgeleri](../ide/xml-documentation-visual-cpp.md)