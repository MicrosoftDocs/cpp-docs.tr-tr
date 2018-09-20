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
ms.openlocfilehash: a39c451bcff7b5b3b1d7dd9f0d3925616b9d6aab
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436233"
---
# <a name="clr-enum-type"></a>CLR Numaralandırma Türü

Bildirimler ve numaralandırmalar davranışını değişti Yönetilen Uzantılar'dan C++ için Visual C++ için.

Yönetilen Uzantılar'numaralandırma bildirimi öncesinde `__value` anahtar sözcüğü. Yerel bir numaralandırma sınıfından türetilen CLR enum ayırmak için buradaki olan `System::ValueType`, benzer bir işlevsellik önerirken oluştu. Örneğin:

```
__value enum e1 { fail, pass };
public __value enum e2 : unsigned short  {
   not_ok = 1024,
   maybe, ok = 2048
};
```

Yeni sözdizimi, ikincisi yerine değer türü kökleri sınıf yapısını vurgulayarak CLR numaralandırmaları ve yerel ayrım sorununu çözer. Bu nedenle, `__value` anahtar sözcüğü atılır, aralıklı anahtar çifti ile değiştirilen `enum class`. Bu, bir başvuru, değer ve arabirim sınıflarından bildirimlerini eşleştirilmiş anahtar sözcüğü simetrisi sağlar:

```
enum class ec;
value class vc;
ref class rc;
interface class ic;
```

Çeviri çiftinin `e1` ve `e2` yeni sözdiziminde şu şekilde görünür:

```
enum class e1 { fail, pass };
public enum class e2 : unsigned short {
   not_ok = 1024,
   maybe, ok = 2048
};
```

Bu küçük söz dizimsel değişiklik dışında CLR numaralandırma türü davranışını çeşitli şekillerde değiştirildi:

- CLR enum İleri dönük bildiriminin artık desteklenmiyor. Eşlemesi yok. Bu, yalnızca bir derleme zamanı hatası işaretlenir.

```
__value enum status; // Managed Extensions: ok
enum class status;   // new syntax: error
```

- Yerleşik aritmetik türleri arasında aşırı yükleme çözünürlüğü ve `Object` sınıf hiyerarşisi iki dil sürümleri arasında ters! Bir yan etkisi olarak CLR numaralandırmaları artık örtük olarak aritmetik türlerine dönüştürülür.

- Yeni sözdiziminde, CLR enum Yönetilen Uzantılar'durumunda değil, kendi kapsamı tutar. Daha önce numaralandırıcılar enum kapsayan kapsamda görünür. Şimdi, numaralandırıcılar enum kapsamı içinde kapsüllenir.

## <a name="clr-enums-are-a-kind-of-object"></a>CLR numaralandırmaları bir nesne türüdür

Aşağıdaki kod parçasını göz önünde bulundurun:

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

Yerel C++ programcısı için doğal hangi örneğinin Aşırı yüklenen sorusuna yanıt `f()` çağrılır, bu `f(int)`. Enum bir sembolik tamsayı sabitidir yanı sıra, bu durumda önceliklidir standart tamsayı yükseltmelerine katılır.  Ve hatta Yönetilen Uzantılar'Bu çağrı çözümler yapılacağı örneği. Biz bunları bir yerel C++ akıl çerçevesinde - ancak biz varolan BCL (temel sınıf kitaplığı) framework ile etkileşim kurmak için bunları gerektiğinde kullanılmadığı zaman bunun nedeni bir dizi sürprizle karşılaşmazsınız - burada bir `Enum` bir sınıf dolaylı olarak türetilir `Object`. Visual C++ dil tasarımında, örneğini `f()` çağrılır, yani `f(Object^)`.

Bunu zorunlu kılmak için Visual C++ tarafından seçmiş CLR numaralandırma türü ve aritmetik türleri arasında örtük dönüştürmeler desteklemeyen bir yöntemdir. Bu, herhangi bir atama aritmetik türü bir CLR enum türünde bir nesnenin açık bir tür dönüştürme gerektiğini anlamına gelir. Bu nedenle, örneğin, verilen

```
void f( int );
```

bir aşırı yüklü olmayan bir yöntem olarak çağrı Yönetilen Uzantılar

```
f( rslt ); // ok: Managed Extensions; error: new syntax
```

Tamam ve içerdiği değer `rslt` örtük olarak bir tamsayı değerine dönüştürülür. Derlemek Visual C++'da, bu çağrı başarısız olur. Doğru bir şekilde çevirmek için bir dönüştürme operatörünün eklemelisiniz:

```
f( safe_cast<int>( rslt )); // ok: new syntax
```

## <a name="the-scope-of-the-clr-enum-type"></a>CLR numaralandırma türü kapsamı

C ve C++ dillerinin arasındaki değişiklikleri c++ yapı özelliğindeki kapsamında ek biriydi. C dilinde bir yapı yalnızca bir arabirimin veya ilişkili bir kapsam desteği olmadan toplama verilerdir. Bu oldukça köklü bir değişiklik zaman ve C dili gelen çok sayıda yeni C++ kullanıcıların bir değişiklikti şeklindeydi. Yerel ve CLR enum arasındaki ilişkiyi benzerdir.

Yönetilen Uzantılar ' yerel bir numaralandırma kapsamında olmaması benzetimini yapmak için zayıf eklenen bir CLR numaralandırıcısının numaralandırıcıların adları tanımlamak için girişimde bulunuldu. Bu başarılı olmamıştır. Sorun, bu ad çakışmalarını yönetmek zor sonuçta genel ad sığdırmaya numaralandırıcıların neden olur. Yeni sözdiziminde, biz diğer CLR dil CLR enum kapsamlarda desteklemek için uygun hale getirdik.

Bu, nitelenmemiş herhangi bir numaralandırıcı bir CLR enum kullanımını yeni sözdizimi tarafından tanınmayacak anlamına gelir. Bir gerçek örneğe göz atalım.

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

Her üç nitelenmemiş bir numaralandırıcı adları kullanır (`(1)`, `(2)`, ve `(3)`) derlemek kaynak kodu için sırayla yeni söz dizimini çeviri nitelendirilmesi gerekir. Özgün kaynak kodunun doğru bir çeviri şu şekildedir:

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

Bu, yerel bir CLR enum arasındaki tasarım stratejisi değiştirir. Bir CLR enum ile ilişkili kapsamı Visual C++'ta Bakımı ne gerekli ya da bir sınıf içinde numaralandırma bildirimi kapsüllemek etkin değil. Bu deyim içinde zil Laboratuvarları povolený 2.0 zamana yakın da genel ad kirlilik sorunu çözmek için geliştirilmiştir.

Özgün beta sürümünde yeni iostream kitaplığı Jerry Schwarz Bell Laboratuarları tarafından Jerry kitaplığı ve gibi ortak numaralandırıcılar için tanımlanan tüm ilişkili kapsüllemedi `read`, `write`, `append`, vb. , kullanıcıların kendi mevcut Kodu derlemek neredeyse imkansız hale. Tek bir çözüm adları gibi çözümlerden olabilirdi `io_read`, `io_write`vb. Enum için kapsam ekleyerek dilini değiştirmek için ikinci bir çözüm olurdu, ancak bu anda mümkün değildi. Orta çözüm sınıf içindeki enum kapsülleyen ya da sınıf hiyerarşisinde nerede kapsayan sınıf kapsamı etiket adı ve numaralandırıcısının numaralandırıcıların doldurmak oluşturmaktı.) Diğer bir deyişle, en az bir başlangıçta içinde sınıflar, numaralandırmalar yerleştirme motivasyon felsefi, değildi, ancak genel ad alanı kirliliği sorun için pratik bir yanıt.

Visual C++ enum ile artık bir sınıf içindeki enum kapsüllemek için bir faydası yoktur. Aslında, bakarsanız `System` ad alanları, numaralandırmalar, sınıflar ve arabirimler tüm aynı bildirim alanında bulunduğunu görürsünüz.

## <a name="see-also"></a>Ayrıca Bkz.

[Değer Türleri ve Davranışları (C++/CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)<br/>
[sabit listesi sınıfı](../windows/enum-class-cpp-component-extensions.md)