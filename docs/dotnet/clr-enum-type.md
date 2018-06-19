---
title: CLR numaralandırma türü | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- scope, of CLR enum
- enum struct keyword [C++]
- enum class keyword [C++]
ms.assetid: 4541d952-97bb-4e35-a7f8-d14f5f6a6606
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2416a306373db08c5e925b4987fc8a9273973c39
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111503"
---
# <a name="clr-enum-type"></a>CLR Numaralandırma Türü
Bildirim ve numaralandırmaları davranışını değişti Yönetilen Uzantılar'dan C++ için Visual C++'a.  
  
 Yönetilen Uzantılar numaralandırma bildiriminin öncesinde `__value` anahtar sözcüğü. Yerel enum sınıfından türetilmiş CLR enum ayırmak için buradaki olan `System::ValueType`, benzer bir işlevsellik öneren oluştu. Örneğin:  
  
```  
__value enum e1 { fail, pass };  
public __value enum e2 : unsigned short  {   
   not_ok = 1024,   
   maybe, ok = 2048   
};  
```  
  
 Yeni sözdizimi, ikincisi yerine değer türü kökleri sınıf yapısını vurgulayarak CLR numaralandırmaları ve yerel ayrım sorununu çözer. Bu nedenle, `__value` anahtar kelimesi atılır aralıklı anahtar çifti ile değiştirilen `enum class`. Bu başvuru, değer ve arabirim sınıflarının bildirimlerine eşleştirilmiş anahtar sözcüğü simetrisi sağlar:  
  
```  
enum class ec;  
value class vc;  
ref class rc;  
interface class ic;  
```  
  
 Numaralandırma çifti çeviri `e1` ve `e2` yeni sözdiziminde aşağıdaki gibi görünür:  
  
```  
enum class e1 { fail, pass };  
public enum class e2 : unsigned short {   
   not_ok = 1024,  
   maybe, ok = 2048   
};  
```  
  
 Bu küçük sözdizimi değişikliğinden dışında CLR numaralandırma türü davranışını çeşitli yollarla değişmiştir:  
  
-   CLR enum ileriye dönük bildirimi artık desteklenmiyor. Eşlemesi yok. Bu, yalnızca bir derleme zamanı hata olarak işaretlenir.  
  
```  
__value enum status; // Managed Extensions: ok  
enum class status;   // new syntax: error  
```  
  
-   Yerleşik aritmetik türleri arasında aşırı yükleme çözünürlüğü ve `Object` sınıf hiyerarşisi iki dil sürümü arasında ters çevrilmiştir! Bir yan etkisi CLR numaralandırmaları artık dolaylı olarak aritmetik türlere dönüştürülür.  
  
-   Yeni sözdiziminde CLR enum Yönetilen Uzantılar durumda değil, kendi kapsamı tutar. Daha önce numaralandırmalar ve enum içeren kapsamında görünür. Şimdi, numaralandırmalar ve enum kapsamı içinde kapsüllenir.  
  
## <a name="clr-enums-are-a-kind-of-object"></a>CLR numaralandırmaları bir nesne türüdür  
 Aşağıdaki kod parçası göz önünde bulundurun:  
  
```  
__value enum status { fail, pass };  
  
void f( Object* ){ Console::WriteLine("f(Object)\n"); }  
void f( int ){ Console::WriteLine("f(int)\n"); }  
  
int main()  
{  
   status rslt = fail;  
  
   f( rslt ); // which f is invoked?  
}  
```  
  
 Yerel C++ programcı için doğal hangi örneğinin aşırı yüklenmiş sorunun yanıtı `f()` çağrılır budur `f(int)`. Enum sembolik bir tamsayı sabiti olduğunda ve, bu durumda öncelikli standart tam sayı yükseltmelerine katılır.  Ve aslında Yönetilen Uzantılar'Bu olduğu çağrının çözümlediği örnek. Biz bunları yerel bir C++ çerçeve of aklınızda - ancak biz bunları varolan BCL (temel sınıf kitaplığı) framework ile etkileşim kurmak için gerekli olduğunda kullanılmadığı zaman bu beklenmeyen durumları - sayısı neden olduğu bir `Enum` bir sınıf dolaylı olarak türetilir `Object`. Visual C++ dili tasarımında örneğini `f()` çağrılan budur `f(Object^)`.  
  
 Visual C++ bu zorlamak için seçtiği bir CLR numaralandırma türü ve aritmetik türleri arasında örtük dönüşümler desteklemeyen bir yoludur. Bu, herhangi bir aritmetik türünün CLR enum türünde bir nesne atama açık atama gerektirecektir anlamına gelir. Bu nedenle, örneğin, verilen  
  
```  
void f( int );  
```  
  
 bir aşırı yüklü olmayan bir yöntem olarak Yönetilen Uzantılar, çağrı  
  
```  
f( rslt ); // ok: Managed Extensions; error: new syntax  
```  
  
 Tamam ve içinde bulunan değer `rslt` örtük olarak bir tamsayı değerine dönüştürülür. Visual C++'da derlemek bu çağrı başarısız olur. Doğru bir şekilde çevirmek için bir dönüşüm işleci eklemelisiniz.  
  
```  
f( safe_cast<int>( rslt )); // ok: new syntax  
```  
  
## <a name="the-scope-of-the-clr-enum-type"></a>CLR Enum Türü kapsamı  
 C ve C++ dilleri arasındaki değişiklikleri birini yapısı tesis kapsamında c++ eklenmesi oluştu. C, yapı yalnızca bir arabirim ya da bir ilişkilendirilmiş kapsam desteği birleşik verilerdir. Bu kök oldukça bir değişiklik zamanında ve C dilinden gelen çok sayıda yeni C++ kullanıcı için bir değişiklikti olmuştur. Yerel ve CLR enum arasındaki ilişkiyi benzerdir.  
  
 Yönetilen Uzantılar'da, bir yerel enum kapsamında yokluğu benzetimini yapmak için bir CLR enum numaralandırıcıları zayıf eklenen adlarını tanımlamak için girişimde bulunuldu. Bu başarılı olmamıştır. Sorun, bu ad çakışmaları yönetmek zor sonuçta genel ad sığdırmaya numaralandırıcılar neden olur. Yeni sözdiziminde biz CLR enum kapsamlarında destekleyen diğer CLR diller için uygun hale getirdik.  
  
 Bu, bir numaralandırıcı CLR enum nitelenmemiş kullanımı yeni sözdizimi tarafından tanınan değil anlamına gelir. Gerçek bir örneğe bakalım.  
  
```  
// Managed Extensions supporting weak injection  
__gc class XDCMake {  
public:  
   __value enum _recognizerEnum {   
      UNDEFINED,  
      OPTION_USAGE,   
      XDC0001_ERR_PATH_DOES_NOT_EXIST = 1,  
      XDC0002_ERR_CANNOT_WRITE_TO = 2,  
      XDC0003_ERR_INCLUDE_TAGS_NOT_SUPPORTED = 3,  
      XDC0004_WRN_XML_LOAD_FAILURE = 4,  
      XDC0006_WRN_NONEXISTENT_FILES = 6,  
   };  
  
   ListDictionary* optionList;  
   ListDictionary* itagList;  
  
   XDCMake() {  
      optionList = new ListDictionary;  
  
      // here are the problems...  
      optionList->Add(S"?", __box(OPTION_USAGE)); // (1)  
      optionList->Add(S"help", __box(OPTION_USAGE)); // (2)  
  
      itagList = new ListDictionary;  
      itagList->Add(S"returns",   
         __box(XDC0004_WRN_XML_LOAD_FAILURE)); // (3)  
   }  
};  
```  
  
 Her üç nitelenmemiş Numaralandırıcı adlarının kullanır (`(1)`, `(2)`, ve `(3)`) derlemek kaynak kodu sırayla yeni sözdizimine çeviri nitelendirilmesi gerekir. Özgün kaynak kodunun doğru çevirisi aşağıdadır:  
  
```  
ref class XDCMake {  
public:  
   enum class _recognizerEnum {  
      UNDEFINED, OPTION_USAGE,   
      XDC0001_ERR_PATH_DOES_NOT_EXIST = 1,  
      XDC0002_ERR_CANNOT_WRITE_TO = 2,  
      XDC0003_ERR_INCLUDE_TAGS_NOT_SUPPORTED = 3,  
      XDC0004_WRN_XML_LOAD_FAILURE = 4,  
      XDC0006_WRN_NONEXISTENT_FILES = 6  
   };  
  
   ListDictionary^ optionList;  
   ListDictionary^ itagList;  
  
   XDCMake() {  
      optionList = gcnew ListDictionary;  
      optionList->Add("?",_recognizerEnum::OPTION_USAGE); // (1)  
      optionList->Add("help",_recognizerEnum::OPTION_USAGE); //(2)  
      itagList = gcnew ListDictionary;  
      itagList->Add( "returns",   
         _recognizerEnum::XDC0004_WRN_XML_LOAD_FAILURE); //(3)  
   }  
};  
```  
  
 Bu, yerel ve CLR enum arasında tasarım stratejisini değiştirir. CLR enum bir ilişkilendirilmiş kapsam Visual C++'ta Bakımı bir ne gerekli ne de bir sınıf içinde enum bildirimi kapsüllemek etkin değil. Bu deyim cfront 2.0 zil laboratuvarlarda içinde süresini geçici de genel ad kirliliği sorunu çözmek için gelişen.  
  
 Özgün beta sürümünde yeni iostream kitaplığı Bell Laboratuarları Jerry Schwarz tarafından Jerry kitaplık ve gibi ortak numaralandırmalar için tanımlanan tüm ilişkili kapsüllemedi `read`, `write`, `append`, vb. , kullanıcıların kendi var olan Kodu derlemek neredeyse imkansız yapılan. Bir çözüm adları gibi çözümlerden olabilirdi `io_read`, `io_write`vb. Kapsam için bir numaralandırma ekleyerek dilini değiştirmek için ikinci bir çözüm olabilirdi, ancak bu zaman mümkün değildi. Orta sınıfı içinde enum kapsülleyen ya da sınıf hiyerarşisinde için çözüm burada kapsayan sınıf kapsamı etiket adı ve numaralandırmalar Enum doldurmak bulunuyordu.) Diğer bir deyişle, sınıflar içinde Enum değerleri en az bir orijinal olarak yerleştirme motivasyon felsefi, değil, ancak genel ad alanı kirliliği problemine pratik yanıt.  
  
 Visual C++ enum ile artık bir sınıftaki bir enum şifreleme için bir faydası yoktur. Aslında, bakarsanız `System` ad alanları, o numaralandırmalar, sınıflar ve arabirimler tüm aynı bildirim alanında bulunduğunu görürsünüz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Değer türleri ve davranışları (C + +/ CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [Enum sınıfı](../windows/enum-class-cpp-component-extensions.md)