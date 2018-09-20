---
title: Normal ifadeler (C + +/ CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- regular expressions [C++]
- .NET Framework [C++], regular expressions
- regular expressions [C++], about regular expressions
- parsing strings [C++]
- examples [C++], strings
- regular expressions [C++], parsing strings
- Split method, parsing strings
- strings [C++], parsing
- substrings, simple matches
- searching, exact substring matches
- strings [C++], exact substring matching
- regular expressions [C++], simple matching
- IsMatch method
- strings [C++], extracting data from
- formatted strings [C++]
- regular expressions [C++], extracting data fields
- data [C++], extracting from strings
- regular expressions [C++], rearranging data
- data [C++], rearranging
- search and replace
- Replace method
- regular expressions [C++], search and replace
- strings [C++], formatting
- data [C++], formatting
- regular expressions [C++], validating data formatting
ms.assetid: 838bab49-0dbc-4089-a604-ef146269ef5a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7f9937d9f93af6179d890f1e9160dd8900cd9f14
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46375621"
---
# <a name="regular-expressions-ccli"></a>Normal İfadeler (C++/CLI)

.NET Framework'teki normal ifade sınıfları kullanarak çeşitli dize işlemleri gösterilmektedir.

Aşağıdaki konular, .NET Framework kullanımını gösteren <xref:System.Text.RegularExpressions> ad alanı (ve bir durumda <xref:System.String.Split%2A?displayProperty=fullName> yöntemi) aramak için ayrıştırma ve dizeleri değiştirin.

## <a name="parse_regex"></a> Normal ifadeler kullanarak dizeleri ayrıştırma

Aşağıdaki kod örneği basit dize kullanarak ayrıştırmayı gösteren <xref:System.Text.RegularExpressions.Regex> sınıfını <xref:System.Text.RegularExpressions?displayProperty=fullName> ad alanı. Birden çok sözcük ayırıcı türü içeren bir dize oluşturulur. Dize, ardından kullanılarak ayrıştırılır <xref:System.Text.RegularExpressions.Regex> sınıfı ile birlikte <xref:System.Text.RegularExpressions.Match> sınıfı. Ardından, her bir sözcüğün cümlenin ayrı olarak görüntülenir.

### <a name="example"></a>Örnek

```cpp
// regex_parse.cpp
// compile with: /clr
#using <system.dll>

using namespace System;
using namespace System::Text::RegularExpressions;

int main( )
{
   int words = 0;
   String^ pattern = "[a-zA-Z]*";
   Console::WriteLine( "pattern : '{0}'", pattern );
   Regex^ regex = gcnew Regex( pattern );

   String^ line = "one\ttwo three:four,five six  seven";
   Console::WriteLine( "text : '{0}'", line );
   for( Match^ match = regex->Match( line );
        match->Success; match = match->NextMatch( ) )
   {
      if( match->Value->Length > 0 )
      {
         words++;
         Console::WriteLine( "{0}", match->Value );
      }
   }
   Console::WriteLine( "Number of Words : {0}", words );

   return 0;
}
```

## <a name="parse_split"></a> Split yöntemini kullanarak dizeleri ayrıştırma

Aşağıdaki kod örneği kullanmayı gösterir <xref:System.String.Split%2A?displayProperty=fullName> yöntemi bir dizedeki her sözcüğün ayıklanamadı. Birden çok sözcük ayırıcı türü içeren bir dize oluşturulur ve ardından çağırarak ayrıştırılmış <xref:System.String.Split%2A> ayırıcıların listesiyle. Ardından, her bir sözcüğün cümlenin ayrı olarak görüntülenir.

### <a name="example"></a>Örnek

```cpp
// regex_split.cpp
// compile with: /clr
using namespace System;

int main()
{
   String^ delimStr = " ,.:\t";
   Console::WriteLine( "delimiter : '{0}'", delimStr );
   array<Char>^ delimiter = delimStr->ToCharArray( );
   array<String^>^ words;
   String^ line = "one\ttwo three:four,five six seven";

   Console::WriteLine( "text : '{0}'", line );
   words = line->Split( delimiter );
   Console::WriteLine( "Number of Words : {0}", words->Length );
   for (int word=0; word<words->Length; word++)
      Console::WriteLine( "{0}", words[word] );

   return 0;
}
```

## <a name="regex_simple"></a> Basit Eşleştirme için normal ifadeleri kullanma

Aşağıdaki kod örneği, tam altdizgi eşleştirmelerin için normal ifadeler kullanır. Arama statik tarafından gerçekleştirilen <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> yöntemi iki dizeyi girdi olarak alır. Birincisi aranacak dize ve ikincisi için aranacak modelidir.

### <a name="example"></a>Örnek

```cpp
// regex_simple.cpp
// compile with: /clr
#using <System.dll>

using namespace System;
using namespace System::Text::RegularExpressions;

int main()
{
   array<String^>^ sentence =
   {
      "cow over the moon",
      "Betsy the Cow",
      "cowering in the corner",
      "no match here"
   };

   String^ matchStr = "cow";
   for (int i=0; i<sentence->Length; i++)
   {
      Console::Write( "{0,24}", sentence[i] );
      if ( Regex::IsMatch( sentence[i], matchStr,
                     RegexOptions::IgnoreCase ) )
         Console::WriteLine("  (match for '{0}' found)", matchStr);
      else
         Console::WriteLine("");
   }
   return 0;
}
```

## <a name="regex_extract"></a> Veri alanlarını ayıklamak için normal ifadeleri kullanma

Aşağıdaki kod örneği, veri biçimlendirilmiş çıkartmak için normal ifadeler kullanımını gösterir. Aşağıdaki kod örneğinde <xref:System.Text.RegularExpressions.Regex> sınıfının bir e-posta adresine karşılık gelen bir desen belirtin. Bu desen, ana bilgisayar adı bölümlerini her e-posta adresi ve kullanıcı almak için kullanılan alan tanımlayıcıları içerir. <xref:System.Text.RegularExpressions.Match> Sınıfı gerçek desen eşleştirme işlemi yapmak için kullanılır. Belirtilen e-posta adresi geçerliyse, kullanıcı adı ve ana bilgisayar adları ayıklanır ve görüntülenir.

### <a name="example"></a>Örnek

```cpp
// Regex_extract.cpp
// compile with: /clr
#using <System.dll>

using namespace System;
using namespace System::Text::RegularExpressions;

int main()
{
    array<String^>^ address=
    {
        "jay@southridgevideo.com",
        "barry@adatum.com",
        "treyresearch.net",
        "karen@proseware.com"
    };

    Regex^ emailregex = gcnew Regex("(?<user>[^@]+)@(?<host>.+)");

    for (int i=0; i<address->Length; i++)
    {
        Match^ m = emailregex->Match( address[i] );
        Console::Write("\n{0,25}", address[i]);

        if ( m->Success )
        {
            Console::Write("   User='{0}'",
            m->Groups["user"]->Value);
            Console::Write("   Host='{0}'",
            m->Groups["host"]->Value);
        }
        else
            Console::Write("   (invalid email address)");
        }

    Console::WriteLine("");
    return 0;
}
```

## <a name="regex_rearrange"></a> Veriyi yeniden düzenlemek için normal ifadeleri kullanma

Aşağıdaki kod örneği, yeniden düzenleyebilir veya verileri yeniden biçimlendirmek için .NET Framework normal ifade Destek'ın nasıl kullanılabileceğini gösterir. Aşağıdaki kod örneğinde <xref:System.Text.RegularExpressions.Regex> ve <xref:System.Text.RegularExpressions.Match> ad ve Soyadı çıkartmak ve bu adı öğelerini ters sırada görüntülemek için sınıflar.

<xref:System.Text.RegularExpressions.Regex> Sınıfı geçerli veri biçimini tanımlayan bir normal ifade oluşturmak için kullanılır. İki ad virgülle ayrılması kabul edilir ve her miktarda beyaz-boşluk, virgül kullanabilirsiniz. <xref:System.Text.RegularExpressions.Match> Yöntemi ardından her bir dizenin analiz etmek için kullanılır. Başarılı olursa, ad ve Soyadı alınır <xref:System.Text.RegularExpressions.Match> nesne ve görüntülenir.

### <a name="example"></a>Örnek

```cpp
// regex_reorder.cpp
// compile with: /clr
#using <System.dll>
using namespace System;
using namespace Text::RegularExpressions;

int main()
{
   array<String^>^ name =
   {
      "Abolrous, Sam",
      "Berg,Matt",
      "Berry , Jo",
      "www.contoso.com"
   };

   Regex^ reg = gcnew Regex("(?<last>\\w*)\\s*,\\s*(?<first>\\w*)");

   for ( int i=0; i < name->Length; i++ )
   {
      Console::Write( "{0,-20}", name[i] );
      Match^ m = reg->Match( name[i] );
      if ( m->Success )
      {
         String^ first = m->Groups["first"]->Value;
         String^ last = m->Groups["last"]->Value;
         Console::WriteLine("{0} {1}", first, last);
      }
      else
         Console::WriteLine("(invalid)");
   }
   return 0;
}
```

## <a name="regex_search"></a> Arama ve değiştirme için normal ifadeleri kullanma

Aşağıdaki kod örneğinde nasıl normal ifade sınıfına <xref:System.Text.RegularExpressions.Regex> arama ve değiştirme yapmak için kullanılabilir. Bunun <xref:System.Text.RegularExpressions.Regex.Replace%2A> yöntemi. Girdi olarak iki dizeyi kullanılan sürümünü alır: değiştirilecek olan dize ve (varsa) yerine bölümleri eklenecek dize için belirtilen desenle eşleşen <xref:System.Text.RegularExpressions.Regex> nesne.

Bu kod, bir dizedeki tüm basamakları alt çizgi (_) değiştirir ve daha sonra bu etkili bir şekilde kaldırarak boş bir dize ile değiştirir. Tek bir adımda aynı etkiyi gerçekleştirilebilir, ancak iki adımı burada tanıtım amacıyla kullanılır.

### <a name="example"></a>Örnek

```cpp
// regex_replace.cpp
// compile with: /clr
#using <System.dll>
using namespace System::Text::RegularExpressions;
using namespace System;

int main()
{
   String^ before = "The q43uick bro254wn f0ox ju4mped";
   Console::WriteLine("original  : {0}", before);

   Regex^ digitRegex = gcnew Regex("(?<digit>[0-9])");
   String^ after = digitRegex->Replace(before, "_");
   Console::WriteLine("1st regex : {0}", after);

   Regex^ underbarRegex = gcnew Regex("_");
   String^ after2 = underbarRegex->Replace(after, "");
   Console::WriteLine("2nd regex : {0}", after2);

   return 0;
}
```

## <a name="regex_validate"></a> Veri biçimlendirmesini doğrulamak için normal ifadeleri kullanma

Aşağıdaki kod örneği, normal ifadeler bir dizeyi formatlamayı doğrulamak için kullanımını gösterir. Aşağıdaki kod örneğinde dize geçerli bir telefon numarası içermelidir. Aşağıdaki kod örneği dizesini kullanır "\d{3}-\d{3}-\d{4}" her bir alan geçerli bir telefon numarası temsil ettiğini göstermek için. Dizesindeki "d" bir basamağı gösterir ve sonra her "d" bağımsız değişkeni bulunması gereken rakam sayısını gösterir. Bu durumda, sayı çizgilerle ayrılmış için gereklidir.

### <a name="example"></a>Örnek

```cpp
// regex_validate.cpp
// compile with: /clr
#using <System.dll>

using namespace System;
using namespace Text::RegularExpressions;

int main()
{
   array<String^>^ number =
   {
      "123-456-7890",
      "444-234-22450",
      "690-203-6578",
      "146-893-232",
      "146-839-2322",
      "4007-295-1111",
      "407-295-1111",
      "407-2-5555",
   };

   String^ regStr = "^\\d{3}-\\d{3}-\\d{4}$";

   for ( int i = 0; i < number->Length; i++ )
   {
      Console::Write( "{0,14}", number[i] );

      if ( Regex::IsMatch( number[i], regStr ) )
         Console::WriteLine(" - valid");
      else
         Console::WriteLine(" - invalid");
   }
   return 0;
}
```

## <a name="related-sections"></a>İlgili Bölümler

[.NET framework normal ifadeleri](/dotnet/standard/base-types/regular-expressions)

## <a name="see-also"></a>Ayrıca Bkz.

[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)