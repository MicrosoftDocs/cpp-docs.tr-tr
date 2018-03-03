---
title: Dizi bildirimleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- multidimensional arrays
- declaring arrays
- arrays [C++], declaring
ms.assetid: 5f958b97-cef0-4058-bbc6-37c460aaed9b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 06742239c48503a5917317a674a39f50a38702c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="array-declarations"></a>Dizi Bildirimleri
Bir "dizisi bildirimi" dizi adları ve öğeleri türünü belirtir. Dizide öğe sayısını da tanımlayabilirsiniz. Dizi türüne sahip bir değişken dizisini öğelerin türü için bir işaretçi olarak kabul edilir.  
  
## <a name="syntax"></a>Sözdizimi  
 `declaration`:  
 *bildirim tanımlayıcıları init bildirimcisi listesi* kabul**;**  
  
 *Init bildirimcisi listesi*:  
 *Init bildirimcisi*  
  
 *Init bildirimcisi listesi* **,***init bildirimcisi*   
  
 *Init bildirimcisi*:  
 *bildirimcisi*  
  
 *bildirimcisi***=***Başlatıcı*   
  
 `declarator`:  
 *İşaretçi* kabul*doğrudan bildirimcisi*  
  
 *doğrudan bildirimcisi*:  
 *doğrudan bildirimcisi***[***sabit ifadesi* kabul**]**   
  
 Çünkü *sabit ifadesi* sözdizimine sahip iki form isteğe bağlıdır:  
  
-   İlk form, bir dizi değişkeni tanımlar. *Sabiti ifade* bağımsız değişkeni köşeli ayraçlar içinde dizide öğe sayısını belirtir. *Sabiti ifade*, varsa, tam sayı türü ve sıfırdan büyük bir değer olmalıdır. Her öğe tarafından verilen türüne sahip *tür belirteci*, dışındaki herhangi bir tür olabilen `void`. Bir dizi öğesine bir işlev türü olamaz.  
  
-   İkinci form başka bir yerde tanımlanmış bir değişken bildirir. Bunu atlar *sabit ifadesi* köşeli ayraçlar, ancak köşeli bağımsız değişkeni. Yalnızca, daha önce bir parametre olarak bildirilen dizi başlatılmadı veya bir dizi başvurusu başka bir yerde açıkça tanımlanmış olarak bildirilen varsa, bu formu kullanabilirsiniz programı.  
  
 Her iki formlarında *doğrudan bildirimcisi* can ve değişken adları değişkenin türünü değiştirin. Köşeli ayraçlar (**[]**) aşağıdaki *doğrudan bildirimcisi* bildirimcisi bir dizi türü için değiştirin.  
  
 Tür niteleyicileri dizi türünde bir nesne bildiriminde görünebilir, ancak niteleyicileri dizi yerine öğeleri için geçerlidir.  
  
 Bu formdaki köşeli parantez içindeki sabit ifadeler listesiyle dizi bildirimcisi izleyerek ("boyutlu" bir diziye) oluşan bir dizi bildirebilirsiniz:  
  
```  
  
type-specifier  
declarator [constant-expression] [constant-expression] ...  
```  
  
 Her *sabit ifadesi* köşeli belirli bir boyut öğe sayısını tanımlar: iki boyutlu diziler sahip iki ayraçlı ifadeler, üç boyutlu diziler üç varsa ve benzeri. Bir parametre olarak bildirilen dizi, başlatılmamış veya bir dizi başvurusu başka bir yerde açıkça tanımlanmış olarak bildirilen, ilk sabit ifadesine kullanmayabilirsiniz programı.  
  
 İşaretçileri dizileri çeşitli nesneleri karmaşık bildirimcileri kullanarak açıklandığı gibi tanımlayabilirsiniz [daha karmaşık Bildirimcileri yorumlama](../c-language/interpreting-more-complex-declarators.md).  
  
 Dizi satır tarafından depolanır. Örneğin, aşağıdaki dizi üç sütun sahip iki satır oluşur:  
  
```  
char A[2][3];  
```  
  
 Üç sütun ilk satırının ilk olarak, ikinci satırın üç sütun tarafından izlenen depolanır. Başka bir deyişle, son alt simge en hızlı bir şekilde değişir.  
  
 Tek bir dizi öğeye başvurmak için bir alt simge ifadesi açıklandığı gibi kullanın [sonek işleçleri](../c-language/postfix-operators.md).  
  
## <a name="examples"></a>Örnekler  
 Bu örneklerde dizi bildirimleri gösterilmektedir:  
  
```  
float matrix[10][15];  
```  
  
 Adlı iki boyutlu dizi `matrix` 150 öğeleri, her sahip olan **float** türü.  
  
```  
struct {  
    float x, y;  
} complex[100];  
```  
  
 Bu yapıların dizi bildirimidir. Bu dizi 100 öğeleri; yine de sahip istiyor musunuz? her öğe, iki üyesi içeren bir yapıdır.  
  
```  
extern char *name[];  
```  
  
 Bu ifade bir dizi işaretçileri adını ve türünü bildirir `char`. Gerçek tanımı `name` başka bir yerde oluşur.  
  
 **Microsoft özel**  
  
 Dizi en büyük boyutunu tutmak için gereken Tamsayı türünde boyutudur **size_t**. Üstbilgi dosyası STDDEF tanımlanır. H **size_t** olan bir `unsigned int` 0x00000000 için 0x7CFFFFFF aralığına sahip.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bildirimler ve Değişken Bildirimleri](../c-language/declarators-and-variable-declarations.md)