---
title: "Ekleme işleçlerini kullanma ve biçimi denetleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: insertion operators
ms.assetid: cdefe986-6548-4cd1-8a67-b431d7d36a1c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2860a0bfd050c4e2a86e948c7008327d237bc5ab
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="using-insertion-operators-and-controlling-format"></a>Ekleme İşleçlerini Kullanma ve Biçimi Denetleme
Bu konuda biçimi denetleme ve ekleme işleçlerini kendi sınıfları için oluşturma gösterilmektedir. Ekleme (**<<**) tüm standart C++ veri türleri için önceden programlanmış, hangi işleci bir çıkış akışı nesneye bayt gönderir. Ekleme işleçlerini "tamsayı bağımsız değişkeni varsayılan biçimi değiştirme öğeleri olan önceden tanımlanmış manipülatörleri ile" çalışır.  
  
 Aşağıdaki seçenekler biçimiyle denetleyebilirsiniz:  
  
- [Çıktı genişliği](#vclrfoutputwidthanchor3)  
  
- [Hizalama](#vclrfalignmentanchor4)  
  
- [Duyarlılık](#vclrfprecisionanchor5)  
  
- [Sayı tabanını](#vclrfradixanchor6)  
  
##  <a name="vclrfoutputwidthanchor3"></a>Çıktı genişliği  
 Çıkış hizalamak için her öğe için çıktı genişliği koyarak belirttiğiniz `setw` manipulator akış veya çağırarak **genişliği** üye işlevi. Bu örnek sağa geniş bir sütun en az 10 karakter değerleri hizalar:  
  
```  
// output_width.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
   double values[] = { 1.23, 35.36, 653.7, 4358.24 };  
   for( int i = 0; i < 4; i++ )  
   {  
      cout.width(10);  
      cout << values[i] << '\n';  
   }  
}  
```  
  
### <a name="output"></a>Çıkış  
  
```  
    1.23 
    35.36 
    653.7 
4358.24  
```  
  
 Öndeki boşlukları herhangi bir değer 10'dan az karakter genişliğinde eklenir.  
  
 Bir alan paneli için kullanmak **dolgu** doldurma karakteri belirtilen genişlik sahip alanlar için değeri ayarlar üye işlevi. Boş disk alanı varsayılandır. Sütundaki sayıların bir yıldız işareti ile paneli, önceki değiştirilecek **için** gibi döngü:  
  
```  
for(int i = 0; i <4; i++)  
{  
    cout.width(10);

 cout.fill('*');

    cout <<values[i] <<endl;  
}  
```  
  
 `endl` Manipulator yeni satır karakteri değiştirir (`'\n'`). Çıktı şu şekildedir:  
  
```  
******1.23  
*****35.36  
*****653.7  
***4358.24  
```  
  
 Genişlikleri veri öğeleri için aynı satırda belirtmek için kullanın `setw` manipulator:  
  
```  
// setw.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iomanip>  
using namespace std;  
  
int main( )  
{  
   double values[] = { 1.23, 35.36, 653.7, 4358.24 };  
   char *names[] = { "Zoot", "Jimmy", "Al", "Stan" };  
   for( int i = 0; i < 4; i++ )  
      cout << setw( 6 )  << names[i]  
           << setw( 10 ) << values[i] << endl;  
}  
```  
  
### <a name="output"></a>Çıkış  
 **Genişliği** üye fonksiyonu içinde bildirilen \<iostream >. Kullanırsanız `setw` veya diğer herhangi bir manipulator bağımsız değişkenlerle eklemelisiniz \<iomanip >. Çıktıda dizeleri 6 genişliğinin bir alan ve 10 genişliğinin bir alandaki tamsayılar yazdırılır:  
  
```  
    Zoot 1.23  
Jimmy     35.36  
    Al 653.7  
    Stan 4358.24  
```  
  
 Ne `setw` ya da **genişliği** değerleri tamsayıya dönüştürür. Biçimlendirilmiş çıkışı varsa genişliği değerin tamamını yazdırır, akışın kesinlik ayarı tabi aşıyor. Her ikisi de `setw` ve **genişliği** yalnızca aşağıdaki alanı etkiler. Alan genişliği döner varsayılan davranışını (gerekli genişlik) bir alan yazdırılan sonra. Ancak, diğer akış biçimlendirme seçeneklerini yürürlükte değiştirilen kadar kalır.  
  
##  <a name="vclrfalignmentanchor4"></a>Hizalama  
 Metni sağa hizalı varsayılan çıkış akışları. Önceki örnekte adları Sola Hizala ve sayıları sağa hizala için yerini **için** gibi döngü:  
  
```  
for (int i = 0; i <4; i++)  
    cout <<setiosflags(ios::left)  
 <<setw(6)  <<names[i]  
 <<resetiosflags(ios::left)  
 <<setw(10) <<values[i] <<endl;  
```  
  
 Çıktı şu şekildedir:  
  
```  
Zoot        1.23  
Jimmy      35.36  
Al         653.7  
Stan     4358.24  
```  
  
 Left-align bayrağı kullanılarak ayarlanır [setiosflags](../standard-library/iomanip-functions.md#setiosflags) manipulator ile `left` Numaralandırıcı. Bu Numaralandırıcı tanımlanan [ios](../standard-library/basic-ios-class.md) kendi başvuru içermelidir nedenle **ios::** öneki. [Resetiosflags](../standard-library/iomanip-functions.md#resetiosflags) manipulator left-align bayrağını devre dışı bırakır. Farklı **genişliği** ve `setw`, etkisini `setiosflags` ve `resetiosflags` kalıcıdır.  
  
##  <a name="vclrfprecisionanchor5"></a>Duyarlılık  
 Kayan nokta duyarlık için varsayılan değer altı ' dir. Örneğin, 3466.9768 numarası 3466.98 yazdırır. Bu değer yazdırma şeklini değiştirmek için kullanın [setprecision](../standard-library/iomanip-functions.md#setprecision) manipulator. İki bayrak manipulator vardır: [sabit](../standard-library/ios-functions.md#fixed) ve [bilimsel](../standard-library/ios-functions.md#scientific). Varsa [sabit](../standard-library/ios-functions.md#fixed) ayarlandığında, 3466.976800 olarak numara yazdırır. Varsa **bilimsel** , bunu yazdırır 3.4669773 + 003 ayarlanmış.  
  
 Gösterilen kayan nokta sayıları görüntülemek için [hizalama](#vclrfalignmentanchor4) önemli bir rakam ile Değiştir **için** gibi döngü:  
  
```  
for (int i = 0; i <4; i++)  
    cout <<setiosflags(ios::left)  
 <<setw(6)    
 <<names[i]  
 <<resetiosflags(ios::left)  
 <<setw(10)   
 <<setprecision(1)  
 <<values[i]   
 <<endl;  
```  
  
 Program, bu liste baskı:  
  
```  
Zoot          1  
Jimmy     4e+001  
Al        7e+002  
Stan      4e+003  
```  
  
 Bilimsel gösterim ortadan kaldırmak için önce bu deyim Ekle **için** döngü:  
  
```  
cout <<setiosflags(ios::fixed);
```  
  
 Sabit gösterimi ile program ile bir rakam ondalık ayırıcıdan sonra yazdırır.  
  
```  
Zoot         1.2  
Jimmy       35.4  
Al         653.7  
Stan      4358.2  
```  
  
 Değiştirirseniz **ios::fixed** bayrağını **ios::scientific**, bu programın yazdırır:  
  
```  
Zoot    1.2e+000  
Jimmy   3.5e+001  
Al      6.5e+002  
Stan    4.4e+003  
```  
  
 Yeniden program bir rakam ondalık ayırıcıdan sonra yazdırır. Her iki **ios::fixed** veya **ios::scientific** , duyarlılık değeri ondalık ayırıcıdan sonra basamak sayısını belirler ayarlanmadı. Hiçbiri bayrağı ayarlarsanız, duyarlılık değeri toplam önemli basamak sayısını belirler. `resetiosflags` Manipulator bu bayrakları temizler.  
  
##  <a name="vclrfradixanchor6"></a>Sayı tabanını  
 **Ara**, **Eki**, ve **onaltılık** manipülatörleri giriş ve çıkış için varsayılan taban ayarlayın. Örneğin, eklerseniz **onaltılık** çıkış akışa nesne manipulator doğru bir onaltılık çıkış biçimi tamsayıların iç veri gösterimine çevirir. Sayıları, a ile f basamağı küçük harf olarak görüntülenen [büyük](../standard-library/ios-functions.md#uppercase) bayrağı (varsayılan) temizleyin; Aksi durumda, büyük harfle görüntülenir. Varsayılan taban olan **Ara** (ondalık).  
  
## <a name="quoted-strings-c14"></a>Tırnak içine alınmış dizeler (C ++ 14)  
 Bir dizeyi bir akışa eklediğinizde, stringstream::str() üye işlevini çağırarak aynı dize kolayca alabilir. Çıkarma işleci akış sonraki bir zamanda yeni bir dize eklemek için kullanmak istiyorsanız, ancak, beklenmeyen bir sonuç çünkü alabilirsiniz >> işleci varsayılan olarak, ilk boşluk karakteri ile karşılaştığında durdurur.  
  
```  
 
std::stringstream ss;  
std::string inserted = "This is a sentence.";  
std::string extracted;  
 
ss <<inserted;  
ss>> extracted;  
 
std::cout <<inserted;     //  This is a sentence.  
std::cout <<extracted;   //   This  
```  
  
 Bu davranış el ile üstesinden gelmek, ancak daha kullanışlı, C ++ 14 dize gidiş yapma ekler `std::quoted` manipulator içinde akış `<iomanip>`. Ekleme, üzerine `quoted()` sınırlayıcı dizesiyle çevreleyen (tırnak ' "' varsayılan olarak) ve ayıklama sırasında son sınırlayıcı karşılaşılanaa kadar tüm karakterleri ayıklamak için akışını yönetir. Tüm Katıştırılmış tırnak bir kaçış karakteriyle kaçışlı ('\\\\' varsayılan olarak).  
  
 Sınırlayıcı yalnızca akış nesnesinde var; Ayıklanan dizesinde mevcut değildir ancak tarafından döndürülen dize mevcut [basic_stringstream::str](../standard-library/basic-stringstream-class.md#str)().  
  
 Tırnak işaretli işleci giriş dizesi bir ham dize olup veya normal bir dize bağımsız olarak yararlı olacak şekilde nasıl bir dize kodda gösterilir ekleme ve çıkarma işlemleri boşluk davranışını bağımsızdır. Giriş dizesi, ne olursa olsun, biçimi katıştırılmış teklifler, satır sonları, sekmeler ve benzeri ve bunların tümü muhafaza edilir quoted() manipulator tarafından.  
  
 Daha fazla bilgi ve tam kod örnekleri, bkz:--brokenlink--[tırnak içine alınmış] (.. / Topic/%3Cios%3E%20functions.md#quoted).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıkış akışları](../standard-library/output-streams.md)   

