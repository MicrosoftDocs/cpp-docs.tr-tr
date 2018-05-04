---
title: Bildirimler ve tanımlar (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 678f1424-e12f-45e0-a957-8169e5fef6cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0f8a0922d66a9421bcc7c6c07b9396b277499d0d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="declarations-and-definitions-c"></a>Bildirimler ve Tanımlar (C++)
Bildirimleri bir program adlarında örneğin değişkenleri, ad alanları, işlevleri ve sınıf adları tanıtır. Bildirimler ayrıca türü bilgilerin yanı sıra diğer bildirilmiş nesne özelliklerini belirtin. Bir ad kullanılabilmesi için bildirilmesi gerekir; C++'da bir ad bildirilmedi noktası derleyiciye görünür olup olmadığını belirler. Bir işlev veya derleme biriminde daha sonraki bir noktada bildirilen sınıf başvuramıyor; kullanabileceğiniz *iletme bildirimleri* bu sınırlamaya geçici alınamıyor.  
  
 Hangi kod veya veri adı açıklar tanımlarını belirtin. Derleme tanımı bildirilmiş şey için depolama alanı ayırdığınızdan olması gerekir.  
  
## <a name="declarations"></a>Bildirimler  
 Bir bildirimi, bir veya daha fazla adları bir programa tanıtır. Bildirimleri bir programda birden çok kez ortaya çıkabilir. Bu nedenle, sınıflar, yapılar, numaralandırılmış türler ve diğer kullanıcı tanımlı türler her derleme birimi için bildirilebilir. Bu birden çok bildiriminde tüm bildirimler aynı sınırlamadır. Bildirimler ayrıca hizmet tanımları, ne zaman dışında olarak bildirimi:  
  
1.  İşlev prototipi (işlev bildirimi hiçbir işlev gövdesi ile) olur.  
  
2.  İçeren `extern` belirticisi ancak hiçbir Başlatıcı (nesneleri ve değişkenleri) veya işlev gövdesi (işlev). Başka bir belirtir, tanım geçerli çeviri biriminde olmak zorunda değildir ve ad dış bağlantı sağlar.  
  
3.  Sınıf bildirimi içinde statik veri üyesi olur.  
  
     Statik sınıf veri üyeleri ayrık sınıfın tüm nesneleri tarafından paylaşılan değişkenleri olduğundan, bunlar gerekir tanımlanabilir ve sınıf bildiriminin dışında başlatıldı. (Sınıflar ve sınıf üyeleri hakkında daha fazla bilgi için bkz: [sınıfları](../cpp/classes-and-structs-cpp.md).)  
  
4.  Bir sınıf adı bildirimi aşağıdaki tanım, olduğu gibi `class T;`.  
  
5.  Olan bir `typedef` deyimi.  
  
 Aynı zamanda tanımları olan bildirimleri örnekleri şunlardır:  
  
```  
// Declare and define int variables i and j.  
int i;  
int j = 10;  
  
// Declare enumeration suits.  
enum suits { Spades = 1, Clubs, Hearts, Diamonds };  
  
// Declare class CheckBox.  
class CheckBox : public Control  
{  
public:  
            Boolean IsChecked();  
    virtual int     ChangeState() = 0;  
};  
```  
  
 Tanımları olmayan bazı bildirimleri şunlardır:  
  
```  
  
extern int i;  
char *strchr( const char *Str, const char Target );  
```  
  
 Kendi bildirimcisi hemen sonra ancak kendi (isteğe bağlı) Başlatıcı önce bildirilmesi için bir ad olarak kabul edilir. Daha fazla bilgi için bkz: [Point of bildirimi](../cpp/point-of-declaration-in-cpp.md).  
  
 Bildirimleri oluşan bir *kapsam*. Kapsam bildirilen ad görünürlüğünü hem de tanımlanan, nesne varsa denetler. Kapsam kuralları bildirimleri ile nasıl etkileşim hakkında daha fazla bilgi için bkz: [kapsam](../cpp/scope-visual-cpp.md).  
  
 Bir nesne bildirimi içerdiği sürece, aynı zamanda bir tanımı olan `extern` depolama sınıfı tanımlayıcısı açıklanan [depolama sınıfları](storage-classes-cpp.md). Bir prototip olmadığı sürece bir işlev bildirimi de bir tanımıdır. Bir prototip tanımlayan bir işlev gövdesi olmadan işlevi başlığıdır. Bir nesne tanımı, depolama ve bu nesne için uygun başlatmaları neden olur.  
  
## <a name="definitions"></a>Tanımlar  
 Bir tanımı, bir nesne değişkeni, işlevi, sınıf veya numaralandırıcı benzersiz bir özelliğidir. Tanımları benzersiz olması gerektiğinden, bir program belirli bir program öğesi için yalnızca tek bir tanım içerebilir. Bildirimler ve tanımlar arasındaki çok bir ilişkiyi olabilir. İçinde bir program öğesi kullanılabilir bildirilen ve tanımlanmamış iki durum vardır:  
  
1.  Bir işlev bildirilen ancak işlev adresi alır bir deyim veya bir işlev çağrısı ile asla başvurulmaz.  
  
2.  Bir sınıf tanımına bilinir gerektirmeyen bir biçimde kullanılır. Ancak, sınıf bildirilmelidir. Aşağıdaki kod, böyle bir durumda gösterir:  
  
    ```  
    // definitions.cpp  
    class WindowCounter;   // Forward declaration; no definition  
  
    class Window  
    {  
       // Definition of WindowCounter not required  
       static WindowCounter windowCounter;  
    };  
  
    int main()  
    {  
    }  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temel kavramlar](../cpp/basic-concepts-cpp.md)   
 [Point of bildirimi](../cpp/point-of-declaration-in-cpp.md)