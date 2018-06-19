---
title: Kopyalama oluşturucuları ve kopya atama işleçleri (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- = operator [C++], copying objects
- assignment statements [C++], copying objects
- assignment operators [C++], for copying objects
- objects [C++], copying
- initializing objects, by copying objects
- copying objects
- assigning values to copy objects
ms.assetid: a94fe1f9-0289-4fb9-8633-77c654002c0d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a1292240e5343c461142e8c6029c277175f6a62f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417268"
---
# <a name="copy-constructors-and-copy-assignment-operators-c"></a>Kopya Oluşturucuları ve Kopya Atama İşleçleri (C++)
> [!NOTE]
>  C ++ 11 başlayarak, iki tür atama dilde desteklenir: *atamayı Kopyala* ve *atama taşıma*. Bu makalede "atama" açıkça tersi belirtilmedikçe kopya atama anlamına gelir. Taşıma atama hakkında daha fazla bilgi için bkz: [taşıma oluşturucuları ve taşıma atama işleçleri (C++)](http://msdn.microsoft.com/en-us/1442de5f-37a5-42a1-83a6-ec9cfe0414db).  
>   
>  Atama işlemi ve başlatma işlemi kopyalanacak nesneleri neden.  
  
-   **Atama**: bir nesnenin değeri başka bir nesneye atandığında, ilk nesne ikinci nesneden kopyalanır. Bu nedenle,  
  
    ```cpp  
    Point a, b;  
    ...  
    a = b;  
    ```  
  
     değeri neden `b` kopyalanmasına `a`.  
  
-   **Başlatma**: yeni bir nesne bildirilmişse bağımsız değişkenleri değere göre işlevlere geçirildiğinde veya değerleri değeriyle işlevlerden döndürüldüğünde başlatma gerçekleşir.  
  
 Sınıf türündeki nesneler için "Kopyala" semantiği tanımlayabilirsiniz. Örneğin, aşağıdaki kodu düşünün:  
  
```cpp  
TextFile a, b;  
a.Open( "FILE1.DAT" );  
b.Open( "FILE2.DAT" );  
b = a;  
```  
  
 Önceki kod "dosya1 içeriğini kopyalayın. anlamına gelebilir Verilerinin dosya2 için. Verilerinin"veya"dosya2 yoksay. anlamına gelebilir Verilerinin ve `b` FILE1.DAT için ikinci bir tanıtıcı. " Aşağıdaki gibi her sınıf için uygun Kopyalama Semantiğini ilişkilendirmeniz gerekir.  
  
-   Atama işleci kullanılarak `operator=` sınıf türü dönüş türü ve tarafından geçirilen parametre olarak bir başvuru birlikte `const` başvuru — örneğin `ClassName& operator=(const ClassName& x);`.  
  
-   Kopya Oluşturucu kullanarak.   
  
 Kopya Oluşturucu bildirmeyin, derleyici member-wise kopya Oluşturucu oluşturur.  Bir kopya atama işleci bildirme derleyici member-wise kopya atama işleci sizin için oluşturur. Kopya Oluşturucu bildirme değil bastırmak derleyicinin ürettiği kopyalama atama işleci ya da bunun tam tersi. Herhangi birini uygularsanız, böylece kodu anlamını açıktır, ayrıca diğeri uygulamanız önerilir.  
   
 Kopya Oluşturucu türünde bir bağımsız değişken alan * sınıfı-name ***&**, burada *sınıf adı* Oluşturucusu tanımlanır sınıfı adı. Örneğin:  
  
```cpp  
// spec1_copying_class_objects.cpp  
class Window  
{  
public:  
    Window( const Window& ); // Declare copy constructor.  
    // ...  
};  
  
int main()  
{  
}  
```  
  
> [!NOTE]
>  Kopya Oluşturucu ait bağımsız değişken türü olun *const sınıfı-ad *** &** mümkün olduğunda. Bu, kopya Oluşturucu içinden kopyalıyor nesne yanlışlıkla değiştirmesini engeller. Ayrıca, kopyalama sağlar **const** nesneleri.  
  
## <a name="compiler-generated-copy-constructors"></a>Oluşturulan derleyici kopya oluşturucuları  
 Kullanıcı tanımlı kopya oluşturucuları gibi derleyicinin ürettiği kopyalama oluşturucular sahip tek bir bağımsız değişken türü "başvuru *sınıf adı*." Kopya oluşturucuları türden tek bir bağımsız değişken alan olarak bildirilen tüm temel sınıflar ve üye sınıfları sahip bir özel durumdur **const** * sınıfı-name ***&**. Böyle bir durumda olmayan derleyicinin ürettiği kopyalama Oluşturucusu ait bağımsız değişken de **const**.  
  
 Kopya Oluşturucu için bağımsız değişken türü olmadığında **const**, kopyalayarak başlatma bir **const** nesne hata oluşturur. Bu durumun tersi geçerli değildir: bağımsız değişken ise **const**, değil bir nesne kopyalayarak başlatabilir **const**.  
  
 Derleyicinin ürettiği atama işleçleri izleyin aynı desen ile regard **const.** Tek bir bağımsız değişken türü aldıkları *sınıfı-ad *** &** tüm temel ve üye sınıflardaki atama işleçleri türü bağımsız değişkenleri almadıkça **const** *sınıf adı &.* Bu durumda, sınıf atama işleci alır oluşturulan bir **const** bağımsız değişkeni.  
  
> [!NOTE]
>  Sanal temel sınıflar, derleyici tarafından oluşturulan veya kullanıcı tanımlı kopya oluşturucular tarafından başlatıldığında, yalnızca bir kez başlatılırlar: Oluşturuldukları noktada.  
  
 Etkileri, kopya oluşturucusununkine benzer. Bağımsız değişken türü olmadığında **const**, bir atama bir **const** nesne hata oluşturur. Tersi geçerli değildir: varsa bir **const** değeri olmayan bir değer atanan **const**, ataması başarılı olur.  
  
 Aşırı yüklenmiş atama işleçleri hakkında daha fazla bilgi için bkz: [atama](../cpp/assignment.md).  
  
