---
description: 'Daha fazla bilgi edinin: normal Ifadeler (C++/CLı)'
title: Normal İfadeler (C++/CLI)
ms.date: 11/04/2016
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
ms.openlocfilehash: 429a121ec7acad46437a344b089f5c6a1ce4243b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245817"
---
# <a name="regular-expressions-ccli"></a>Normal İfadeler (C++/CLI)

.NET Framework normal ifade sınıflarını kullanarak çeşitli dize işlemlerini gösterir.

Aşağıdaki konularda, <xref:System.Text.RegularExpressions> <xref:System.String.Split%2A?displayProperty=fullName> dizeleri aramak, ayrıştırmak ve değiştirmek için .NET Framework ad alanı (ve bir durumda yöntemi) kullanımı gösterilmektedir.

## <a name="parse-strings-using-regular-expressions"></a><a name="parse_regex"></a> Normal Ifadeler kullanarak dizeleri ayrıştırma

Aşağıdaki kod örneği, <xref:System.Text.RegularExpressions.Regex> ad alanındaki sınıfını kullanarak basit dize ayrıştırmayı gösterir <xref:System.Text.RegularExpressions?displayProperty=fullName> . Birden çok sözcük ayırıcı türü içeren bir dize oluşturulur. Daha sonra dize, sınıfıyla birlikte sınıfı kullanılarak ayrıştırılır <xref:System.Text.RegularExpressions.Regex> <xref:System.Text.RegularExpressions.Match> . Ardından, tümcedeki her sözcük ayrı olarak görüntülenir.

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

## <a name="parse-strings-using-the-split-method"></a><a name="parse_split"></a> Split yöntemini kullanarak dizeleri ayrıştırma

Aşağıdaki kod örneği, <xref:System.String.Split%2A?displayProperty=fullName> bir dizeden her bir sözcüğü ayıklamak için yöntemini kullanmayı gösterir. Birden çok sözcük ayırıcı türü içeren bir dize oluşturulur ve ardından <xref:System.String.Split%2A> ayırıcıların bir listesiyle çağırarak ayrıştırılır. Ardından, tümcedeki her sözcük ayrı olarak görüntülenir.

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

## <a name="use-regular-expressions-for-simple-matching"></a><a name="regex_simple"></a> Basit eşleştirme için normal Ifadeler kullanın

Aşağıdaki kod örneği, tam alt dize eşleşmelerini aramak için normal ifadeler kullanır. Arama, <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> giriş olarak iki dizeyi alan statik yöntem tarafından gerçekleştirilir. İlki Aranmak üzere dize, ikincisi ise aranacak bir modeldir.

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

## <a name="use-regular-expressions-to-extract-data-fields"></a><a name="regex_extract"></a> Veri alanlarını ayıklamak için normal Ifadeleri kullanma

Aşağıdaki kod örneği, biçimli bir dizeden veri ayıklamak için normal ifadelerin kullanımını gösterir. Aşağıdaki kod örneği, <xref:System.Text.RegularExpressions.Regex> bir e-posta adresine karşılık gelen bir model belirtmek için sınıfını kullanır. Bu, her bir e-posta adresinin Kullanıcı ve ana bilgisayar adı bölümlerini almak için kullanılabilen alan tanımlayıcılarını içerir. <xref:System.Text.RegularExpressions.Match>Sınıfı, gerçek model eşleştirmeyi gerçekleştirmek için kullanılır. Verilen e-posta adresi geçerliyse, Kullanıcı adı ve ana bilgisayar adları ayıklanır ve görüntülenir.

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

## <a name="use-regular-expressions-to-rearrange-data"></a><a name="regex_rearrange"></a> Verileri yeniden düzenlemek için normal Ifadeleri kullanma

Aşağıdaki kod örneği, .NET Framework düzenli ifade desteğinin verileri yeniden düzenlemek veya yeniden biçimlendirmek için nasıl kullanılabileceğini gösterir. Aşağıdaki kod örneği, <xref:System.Text.RegularExpressions.Regex> <xref:System.Text.RegularExpressions.Match> bir dizeden ilk ve son isimleri ayıklamak için ve sınıflarını kullanır ve ardından bu ad öğelerini ters sırada görüntüler.

<xref:System.Text.RegularExpressions.Regex>Sınıfı, verilerin geçerli biçimini açıklayan bir normal ifade oluşturmak için kullanılır. İki ad, virgülle ayrılmış olarak kabul edilir ve virgül etrafında herhangi bir boşluk içerebilir. <xref:System.Text.RegularExpressions.Match>Yöntemi daha sonra her dizeyi çözümlemek için kullanılır. Başarılı olursa, ilk ve son adlar <xref:System.Text.RegularExpressions.Match> nesneden alınır ve görüntülenir.

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

## <a name="use-regular-expressions-to-search-and-replace"></a><a name="regex_search"></a> Arama ve değiştirme için normal Ifadeleri kullanma

Aşağıdaki kod örneği, normal ifade sınıfının <xref:System.Text.RegularExpressions.Regex> arama ve değiştirme işlemleri için nasıl kullanılabileceğini gösterir. Bu yöntem ile yapılır <xref:System.Text.RegularExpressions.Regex.Replace%2A> . Kullanılan sürüm, giriş olarak iki dize alır: değiştirilecek dize ve nesneye verilen Düzenle eşleşen bölümlerin (varsa) yerine eklenecek dize <xref:System.Text.RegularExpressions.Regex> .

Bu kod, bir dizedeki tüm rakamları alt çizgi (_) ile değiştirir ve ardından bunları boş bir dizeyle değiştirir ve bunları etkin bir şekilde kaldırır. Aynı efekt tek bir adımda gerçekleştirilebilir, ancak burada tanıtım amacıyla iki adım kullanılır.

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

## <a name="use-regular-expressions-to-validate-data-formatting"></a><a name="regex_validate"></a> Veri biçimlendirmesini doğrulamak için normal Ifadeleri kullanma

Aşağıdaki kod örneği, bir dizenin biçimlendirilmesini doğrulamak için normal ifadelerin kullanımını gösterir. Aşağıdaki kod örneğinde, dize geçerli bir telefon numarası içermelidir. Aşağıdaki kod örneği, {3} {3} {4} her alanın geçerli bir telefon numarasını temsil ettiğini göstermek için "\d-\d-\d" dizesini kullanır. Dizedeki "d" bir basamağı gösterir ve her bir "d" öğesinin ardından gelen bağımsız değişken bulunması gereken basamak sayısını gösterir. Bu durumda, sayının tirelere göre ayrılması gerekir.

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

[.NET Framework Normal İfadeleri](/dotnet/standard/base-types/regular-expressions)

## <a name="see-also"></a>Ayrıca bkz.

[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
