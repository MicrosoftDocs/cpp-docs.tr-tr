---
description: Hakkında daha fazla bilgi edinin:. XML dosyası Işleme
title: .Xml Dosyası İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- XML documentation, processing XML file
ms.assetid: e70fdeae-80ac-4872-ab24-771c5635cfbf
ms.openlocfilehash: ded4551adcc4bec4aef27fe38f47470065ea9ef4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192700"
---
# <a name="xml-file-processing"></a>.Xml Dosyası İşleme

Derleyici, kodunuzda belge oluşturmak için etiketlenmiş her yapı için bir KIMLIK dizesi oluşturur. Daha fazla bilgi için bkz. [Önerilen Etiketler belge açıklamaları](recommended-tags-for-documentation-comments-visual-cpp.md). KIMLIK dizesi yapıyı benzersiz bir şekilde tanımlar. . Xml dosyasını işleyen programlar, belgenin uygulandığı karşılık gelen .NET Framework meta verilerini veya yansıma öğesini tanımlamak için KIMLIK dizesini kullanabilir.

. Xml dosyası, kodunuzun hiyerarşik bir gösterimi değildir, her öğe için oluşturulan KIMLIĞE sahip düz bir liste olur.

Derleyici, KIMLIK dizelerini oluşturduğunda aşağıdaki kuralları sunar:

- Dizeye boşluk yerleştirilmez.

- KIMLIK dizesinin ilk bölümü, tanımlanmakta olan üyenin türünü tanımlar, tek bir karakter ve iki nokta üst üste gelir. Aşağıdaki üye türleri kullanılır:

  | Karakter | Açıklama |
  |---------------|-----------------|
  | N | ad alanı<br /><br /> Bir ad alanına belge açıklamaları ekleyemezsiniz, bir ad alanına cref başvuruları mümkündür. |
  | T | Tür: Class, Interface, struct, Enum, Delegate |
  | D |  typedef |
  | F | alan |
  | P | Özellik (Dizin oluşturucular veya diğer dizinli özellikler dahil) |
  | M | Yöntem (oluşturucular, işleçler ve benzeri özel yöntemler dahil) |
  | E | event |
  | ! | hata dizesi<br /><br /> Dizenin geri kalanı hata hakkında bilgi sağlar. MSVC derleyicisi çözümlenemeyen bağlantılar için hata bilgileri oluşturur. |

- Dizenin ikinci bölümü, ad alanının köküden başlayarak öğenin tam nitelikli adıdır. Öğenin adı, kapsayan türü veya türleri ve ad alanı noktalarla ayrılır. Öğenin adında nokta varsa, bunlar karma işareti (' # ') ile değiştirilmiştir. Hiçbir öğenin doğrudan adında bir karma işareti olmadığı varsayılır. Örneğin, oluşturucunun tam adı `String` "System. String. #ctor" olacaktır.

- Özellikler ve yöntemler için, yöntem için bağımsız değişkenler varsa, parantez içine alınmış bağımsız değişken listesi aşağıda verilmiştir. Bağımsız değişken yoksa, parantezler yok. Bağımsız değişkenler virgülle ayrılır. Her bağımsız değişkenin kodlaması, .NET Framework imzasında nasıl kodlandığını doğrudan izler:

  - Temel türler. Normal türler (ELEMENT_TYPE_CLASS veya ELEMENT_TYPE_VALUETYPE), türün tam adı olarak gösterilir.

  - İç türler (örneğin, ELEMENT_TYPE_I4, ELEMENT_TYPE_OBJECT, ELEMENT_TYPE_STRING ELEMENT_TYPE_TYPEDBYREF. ve ELEMENT_TYPE_VOID), karşılık gelen tam türün tam adı olarak gösterilir, örneğin, **System. Int32** veya **System. TypedReference**.

  - ELEMENT_TYPE_PTR, değiştirilen türü takip eden bir ' * ' olarak temsil edilir.

  - ELEMENT_TYPE_BYREF, \@ değiştirilen türden sonra ' ' olarak gösterilir.

  - ELEMENT_TYPE_PINNED, değiştirilen türden sonra bir ' ^ ' olarak temsil edilir. MSVC derleyicisi bunu hiçbir şekilde oluşturmaz.

  - ELEMENT_TYPE_CMOD_REQ, değiştirilen türü takip eden bir ' &#124; ' ve değiştirici sınıfının tam adı olarak temsil edilir. MSVC derleyicisi bunu hiçbir şekilde oluşturmaz.

  - ELEMENT_TYPE_CMOD_OPT, değiştirilen türü takip eden bir '! ' ve değiştirici sınıfının tam adı olarak temsil edilir.

  - ELEMENT_TYPE_SZARRAY, dizinin öğe türü takip eden "[]" olarak temsil edilir.

  - ELEMENT_TYPE_GENERICARRAY, dizinin öğe türü takip eden "[?]" olarak temsil edilir. MSVC derleyicisi bunu hiçbir şekilde oluşturmaz.

  - Element_type_array, `size` virgül sayısının derece-1 olduğu ve bilindiğinde her boyutun alt sınırları ve boyutunun ondalık olarak temsil edildiği [küçük harfe göre:, küçük *harf sınırı*:] olarak temsil edilir `size` . Daha düşük bir sınır veya boyut belirtilmemişse, bu yalnızca atlanır. Belirli bir boyutun alt sınırı ve boyutu atlanırsa, ': ' de atlanır. Örneğin, alt sınır olarak 1 olan 2 boyutlu bir dizi ve belirtilmemiş boyutlar [1:, 1:].

  - ELEMENT_TYPE_FNPTR, `type`  `type` dönüş türü olduğu ve *imza* YÖNTEMIN bağımsız değişkenlerinin olduğu "= Func: (Signature)" olarak temsil edilir. Bağımsız değişken yoksa, parantezler atlanır. MSVC derleyicisi bunu hiçbir şekilde oluşturmaz.

  Aşağıdaki imza bileşenleri, aşırı yüklenmiş yöntemlerin farklılaştırmaları hiçbir şekilde kullanıldıklarından temsil edilmez:

  - çağırma kuralı

  - dönüş türü

  - ELEMENT_TYPE_SENTINEL

- Yalnızca dönüştürme işleçleri için, metodun dönüş değeri, daha önce kodlanmış olarak ' ~ ' ve dönüş türü tarafından kodlanır.

- Genel türler için, türün adının ardından bir geri değer ve ardından genel tür parametrelerinin sayısını belirten bir sayı olacaktır.  Örneğin,

    ```xml
    <member name="T:MyClass`2">
    ```

  Olarak tanımlanan bir tür için `public class MyClass<T, U>` .

  Genel türleri parametre olarak alan yöntemler için genel tür parametreleri, geri işaretleri (örneğin \` , 0, 1) ile önceden ortaya çıkacak sayılar olarak belirtilir \` .  Türün genel parametreleri için sıfır tabanlı dizi gösterimini temsil eden her bir sayı.

## <a name="example"></a>Örnek

Aşağıdaki örneklerde, bir sınıf ve üyeleri için KIMLIK dizelerinin nasıl oluşturulacağı gösterilmektedir.

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

## <a name="see-also"></a>Ayrıca bkz.

[XML Belgeleri](xml-documentation-visual-cpp.md)
