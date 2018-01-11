---
title: "Çıkış dosya akışı üye işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: output streams [C++], member functions
ms.assetid: 38aaf710-8035-4a34-a0c4-123a5327f28a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 25313cce5d032c4c3975fffbf8ca89b232031661
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="output-file-stream-member-functions"></a>Çıkış Dosya Akışı Üye İşlevleri
Çıkış akışı üye işlevleri sahip üç tür: manipülatörleri için biçimlendirilmemiş gerçekleştirmesi eşdeğer olan yazma işlemleri ve aksi takdirde akış değiştiren bu durum ve herhangi bir eşdeğer manipulator veya ekleme işleci sahip. Sıralı, biçimlendirilmiş çıkışı için yalnızca ekleme işleçlerini ve manipülatörleri kullanabilirsiniz. Rasgele erişim ikili disk çıktı için diğer üye işlevleri ile veya olmadan ekleme işleçlerini kullanın.  
  
## <a name="the-open-function-for-output-streams"></a>Çıkış akışları için açık işlevi  
 Çıkış dosya akışı kullanmak için ([ofstream](../standard-library/basic-ofstream-class.md)), bu akış oluşturucuda belirli bir disk dosyası ile ilişkilendirmeniz gerekir veya **açmak** işlevi. Kullanırsanız **açmak** işlevi, bir dizi dosyası ile aynı stream nesnesi yeniden kullanabilirsiniz. Her iki durumda da, aynı dosya açıklayan bağımsız değişkenler.  
  
 Bir çıkış akışı ile ilişkilendirilmiş dosyayı açtığınızda, genellikle belirttiğiniz bir **open_mode** bayrağı. Numaralandırmalar içinde olarak tanımlanan bu bayraklar birleştirebilirsiniz `ios` bit düzeyinde OR (&#124;) ile sınıfının işleci. Bkz: [ios_base::openmode](../standard-library/ios-base-class.md#openmode) numaralandırıcılar listesi.  
  
 Üç ortak çıkış akış durumları modu seçenekleri içerir:  
  
-   Bir dosya oluşturma. Dosya zaten mevcutsa, eski sürüm silinir.  
  
 ```  
    ostream ofile("FILENAME");
// Default is ios::out  
    ofstream ofile("FILENAME", ios::out);

// Equivalent to above  
```  
  
-   Varolan bir dosyaya kaydeder ekleme veya henüz yoksa bir tane.  
  
 ```  
    ofstream ofile("FILENAME", ios::app);
```  
  
-   İki dosyalarda, bir seferde bir aynı akışı açılamadı.  
  
 ```  
    ofstream ofile();
ofile.open("FILE1",
    ios::in);
// Do some output  
    ofile.close();

// FILE1 closed  
    ofile.open("FILE2",
    ios::in);
// Do some more output  
    ofile.close();

// FILE2 closed  // When ofile goes out of scope it is destroyed.  
```  
  
## <a name="the-put"></a>Put
 **Put** işlevi bir karakter çıkış akışına yazar. Aşağıdaki iki ifadeleri varsayılan olarak aynıdır, ancak ikinci akışın biçimi değişkenleriyle etkilenir:  
  
```  
cout.put('A');

// Exactly one character written  
cout <<'A'; // Format arguments 'width' and 'fill' apply   
```  
  
## <a name="the-write"></a>Yazma
 **Yazma** işlevi bir bellek bloğu çıkış dosyası akışına yazar. Length bağımsız yazılan bayt sayısını belirtir. Bu örnek bir çıkış dosya akışı oluşturur ve ikili değeri Yazar `Date` ona yapısı:  
  
```  
// write_function.cpp  
// compile with: /EHsc  
#include <fstream>  
using namespace std;  
  
struct Date  
{  
   int mo, da, yr;  
};  
  
int main( )  
{  
   Date dt = { 6, 10, 92 };  
   ofstream tfile( "date.dat" , ios::binary );  
   tfile.write( (char *) &dt, sizeof dt );  
}  
```  
  
 **Yazma** işlevi değil Durdur tüm sınıf yapısı yazıldığı şekilde bir null karakter ulaştığı zaman. İşlev iki bağımsız değişkeni alır: bir `char` işaretçi ve yazmak için karakter sayısı. Gerekli dönüştürme Not **char\***  yapısı nesnesinin adresini önce.  
  
## <a name="the-seekp-and-tellp-functions"></a>Seekp ve tellp işlevleri  
 Çıkış dosya akışı veri sonraki yazılacak nerede konumuna işaret eden bir iç işaretçi tutar. `seekp` Üye işlevi bu işaretçinin ayarlar ve bu nedenle rasgele erişim disk dosya çıktısı sağlar. `tellp` Üye işlevi sırasında dosya konumunu döndürür. Giriş akışı eşdeğerlerini kullanın örnekleri için `seekp` ve `tellp`, bkz: [seekg ve tellg işlevleri](../standard-library/input-stream-member-functions.md).  
  
## <a name="the-close-function-for-output-streams"></a>Çıkış akışları için Kapat işlevi  
 **Kapatmak** üye işlevi bir çıkış dosya akışı ile ilişkili disk dosyası kapatır. Dosyanın tüm disk çıkış tamamlamak için kapalı olmalıdır. Gerekirse, `ofstream` yıkıcı kapatır dosya, ancak kullanabilirsiniz **kapatmak** aynı stream nesnesi için başka bir dosyayı açmaya gerekiyorsa işlev.  
  
 Çıkış akışı yıkıcı bir akışın dosyası eksikse Oluşturucusu otomatik olarak kapatılır. veya **açmak** üye işlevi dosya açılır. Zaten açık dosya veya kullanım için dosya tanımlayıcısı oluşturucusu başarılı olursa **attach** üye işlevi, dosyanın açıkça kapatmanız gerekir.  
  
##  <a name="vclrferrorprocessingfunctionsanchor10"></a>Hata işleme işlevleri  
 Bir akışa yazılırken hataları test etmek için bu üye işlevleri kullanın:  
  
|İşlev|Dönüş değeri|  
|--------------|------------------|  
|[hatalı](http://msdn.microsoft.com/Library/4038d331-e9c9-48b0-bf49-c6505744469c)|Döndürür **true** kurtarılamaz bir hata varsa.|  
|[başarısız](http://msdn.microsoft.com/Library/619f1b36-1e72-4551-8b48-888ae4e370d2)|Döndürür **true** kurtarılamaz bir hata ya da bir dönüştürme hatası gibi "beklenen" bir koşul ise veya dosya bulunamadı. İşleme genellikle çağrısı yapıldıktan sonra devam **temizleyin** bir sıfır bağımsız değişkeni ile.|  
|[iyi](http://msdn.microsoft.com/Library/77f0aa17-2ae1-48ae-8040-592d301e3972)|Döndürür **true** (kurtarılamaz veya diğer) hata koşulu yok ve dosya sonu bayrağı ayarlı değil.|  
|[eof](http://msdn.microsoft.com/Library/3087f631-1268-49cd-86cf-ff4108862329)|Döndürür **true** dosya sonu koşulunu.|  
|[Temizle](http://msdn.microsoft.com/Library/dc172694-1267-45f8-8f5c-e822e16fc271)|İç hata durumuna ayarlar. Varsayılan bağımsız değişkenler olarak adlandırılan, tüm hata BITS temizler.|  
|[rdstate](http://msdn.microsoft.com/Library/e235e4e2-7e95-4777-a160-3938d263dd9c)|Geçerli hata durumuna döndürür.|  
  
 **!** İşleç aşırı yüklenmiş aynı işlevi gerçekleştirmek için **başarısız** işlevi. Bu nedenle ifade:  
  
```  
if(!cout)...  
```  
  
 eşdeğerdir:  
  
```  
if(cout.fail())...  
```  
  
 **Void\*()** işleci aşırı yüklenmiş tersi olacak şekilde **!** işleç; Bu nedenle ifade:  
  
```  
if(cout)...  
```  
  
 eşittir:  
  
```  
if(!cout.fail())...  
```  
  
 **Void\*()** işleci eşit değil **iyi** çünkü dosya sonu için test değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıkış Akışları](../standard-library/output-streams.md)

