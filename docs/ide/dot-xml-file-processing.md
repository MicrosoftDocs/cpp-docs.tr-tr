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
ms.openlocfilehash: 1cf6f5660e1aaeaeff4050bb80009eda7d14c3ba
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33340521"
---
# <a name="xml-file-processing"></a>.Xml Dosyası İşleme
Derleyici kodunuzda belgeleri oluşturmak için etiketli her yapı için bir kimlik dizesi oluşturur. Daha fazla bilgi için bkz: [önerilen etiketler belge açıklamaları](../ide/recommended-tags-for-documentation-comments-visual-cpp.md). Kimlik dizesi, yapı benzersiz olarak tanımlar. .Xml dosyası işleme programları kimlik dizesi belgelere uygulandığı karşılık gelen .NET Framework meta verileri veya yansıma öğesi tanımlamak için kullanabilirsiniz.  
  
 .Xml dosyasını kodunuzun hiyerarşik bir temsili olmadığından, düz bir liste her öğe için oluşturulan kimliği.  
  
 Kimlik dizeleri oluşturduğunda derleyici aşağıdaki kurallara uyan:  
  
-   Hiçbir boşluk dizesi içinde yer alır.  
  
-   Kimlik dizesi ilk bölümü, izleyen iki nokta ile tek bir karakter ile tanımlanmasını üye türünü tanımlar. Aşağıdaki üye türleri kullanılır:  
  
    |Karakter|Açıklama|  
    |---------------|-----------------|  
    |N|ad alanı<br /><br /> Belge açıklamaları için bir ad alanı ekleyemezsiniz, bir ad alanı cref başvurular mümkündür.|  
    |T|Tür: sınıf, arabirim, yapı, enum, temsilci|  
    |D|typedef|  
    |F|alan|  
    |P|özellik (dizin oluşturucular veya diğer Dizinli Özellikler dahil)|  
    |M|(Bu tür özel yöntemleri Oluşturucular, işleçler ve diğerleri dahil) yöntemi|  
    |E|olay|  
    |!|Hata dizesi<br /><br /> Dizenin geri kalanı hata hakkında bilgi sağlar. Visual C++ derleyicisi çözümlenemiyor bağlantılar için hata bilgilerini oluşturur.|  
  
-   İkinci dize ad alanı kökünde başlayan öğesi, tam adını parçasıdır. Öğesi, kendi kapsayan türü veya türleri ve ad alanı adını noktalarla ayrılmış. Öğesinin adı nokta varsa, karma-işareti ('#') yerini alır. Öğe adını doğrudan bir karma oturum olduğunu varsayılır. Örneğin, tam adını `String` Oluşturucusu "System.String.#ctor" olacaktır.  
  
-   Yöntemi için bağımsız değişkeni varsa özellikleri ve yöntemleri için ayraç içinde bağımsız değişken listesi aşağıdadır. Bağımsız değişkenler varsa, hiçbir parantez yok. Bağımsız değişkenler virgülle ayrılır. Her bağımsız değişkeni kodlama doğrudan bir .NET Framework imzada nasıl kodlanmış aşağıdaki gibidir:  
  
    -   Taban türleri. Normal türleri (ELEMENT_TYPE_CLASS veya ELEMENT_TYPE_VALUETYPE) türünün tam adını temsil edilir.  
  
    -   İç türleri (örneğin, ELEMENT_TYPE_I4, ELEMENT_TYPE_OBJECT, ELEMENT_TYPE_STRING, ELEMENT_TYPE_TYPEDBYREF dizisi. ve ELEMENT_TYPE_VOID) karşılık gelen tam türünü, tam adıyla örneğin temsil **System.Int32** veya **System.TypedReference**.  
  
    -   ELEMENT_TYPE_PTR olarak temsil edilir bir ' *' değiştirilmiş türü aşağıdaki.  
  
    -   ELEMENT_TYPE_BYREF olarak temsil edilir bir ' @' değiştirilmiş türü aşağıdaki.  
  
    -   ELEMENT_TYPE_PINNED olarak temsil edilir bir ' ^' değiştirilmiş türü aşağıdaki. Visual C++ Derleyici hiçbir zaman bu oluşturur.  
  
    -   ELEMENT_TYPE_CMOD_REQ olarak temsil edilir bir '&#124;' ve değiştirilen türü aşağıdaki değiştiricisi sınıfın tam adı. Visual C++ Derleyici hiçbir zaman bu oluşturur.  
  
    -   ELEMENT_TYPE_CMOD_OPT olarak temsil edilir bir '!' ve değiştirilen türü aşağıdaki değiştiricisi sınıfın tam adı.  
  
    -   ELEMENT_TYPE_SZARRAY "dizi öğesi türü aşağıdaki []" gösterilir.  
  
    -   ELEMENT_TYPE_GENERICARRAY "[?]" temsil edilir dizi öğesi türü aşağıdaki. Visual C++ Derleyici hiçbir zaman bu oluşturur.  
  
    -   ELEMENT_TYPE_ARRAY olarak temsil edilir [*lowerbound*:`size`,*lowerbound*:`size`] Burada virgül sayısı ise derecesini - 1 ve alt sınırlarını ve her boyut boyutu bilinen ondalık olarak temsil edilir. Alt sınır veya boyutu belirtilmezse, yalnızca atlanır. Belirli bir boyut için boyut ve alt sınır atlanırsa, ':' de atlanır. Örneğin, 1 belirtilmeyen boyutları ve alt sınırlarını olarak 2 boyutlu bir dizi olduğundan [1:, 1:].  
  
    -   ELEMENT_TYPE_FNPTR olarak temsil edilir "FUNC =:`type`(*imza*)", burada `type` dönüş türü ve *imza* olan yöntemi değişkendir. Bağımsız değişkenler varsa, parantez göz ardı edilir. Visual C++ Derleyici hiçbir zaman bu oluşturur.  
  
     Hiçbir zaman farklılaştırıcı aşırı yüklenmiş yöntemler için kullanılan çünkü aşağıdaki imza bileşenleri temsil edilmez:  
  
    -   Çağırma kuralı  
  
    -   Dönüş türü  
  
    -   ELEMENT_TYPE_SENTINEL  
  
-   Yalnızca dönüştürme işleçleri için yönteminin dönüş değeri olarak kodlanmış bir ' ~' daha önce kodlanmış dönüş türü, izlemelidir.  
  
-   Genel türler için türünün adı geri değer çizgilerinin ve ardından genel tür parametre sayısını belirten bir sayı tarafından izlenir.  Örneğin,  
  
    ```  
    <member name="T:MyClass`2">  
    ```  
  
     Olarak tanımlanan bir tür için `public class MyClass<T, U>`.  
  
     Geri çizgilerine ile başlayan sayılar olarak belirtilen parametre olarak genel türler alma yöntemlerinin için genel tür parametreleri (örneğin \`0, \`1).  Genel tür parametreleri için sıfır tabanlı bir dizi gösterimi gösteren her bir sayı.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekler nasıl kimliği için bir sınıf dizeleri ve üyeleri oluşturulur.  
  
```  
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