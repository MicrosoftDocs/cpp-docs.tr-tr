---
title: "Nasıl yapılır: bir derlemeden STL/CLR kapsayıcı kullanıma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- STL/CLR Containers [STL/CLR]
- STL/CLR, cross-assembly issues
ms.assetid: 87efb41b-3db3-4498-a2e7-f3ef8a99f04d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b47e59e5b0c14bc0014140da67d226d62fad02ba
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-expose-an-stlclr-container-from-an-assembly"></a>Nasıl yapılır: Bir Derlemeden STL/CLR Kapsayıcısı Sunma
STL/CLR kapsayıcıları gibi `list` ve `map` şablon ref sınıfları uygulanır. C++ şablonları derleme zamanında örneği için tam olarak aynı imzaya sahip, ancak farklı derlemelerde olan iki şablon sınıfları gerçekte farklı türleridir. Bu şablon sınıfları derleme sınırlarında kullanılamaz anlamına gelir.  
  
 STL/CLR kapsayıcıları çapraz derleme paylaşımı mümkün kılmak için genel arabirimini uygulayan <xref:System.Collections.Generic.ICollection%601>. Bu genel arabirimini kullanarak genel türler, C++, C# ve Visual Basic dahil olmak üzere destek tüm diller STL/CLR kapsayıcıları erişebilir.  
  
 Bu konu adlı bir C++ derlemede yazılmış çok STL/CLR kapsayıcı öğeleri görüntülemek nasıl gösterir `StlClrClassLibrary`. Erişim için iki derleme gösteriyoruz `StlClrClassLibrary`. İlk derleme C++ ve C# ikinci yazılır.  
  
 Her iki derlemeleri C++ ile yazılmış, kullanarak bir kapsayıcı genel arabiriminin erişebilirsiniz kendi `generic_container` typedef. Örneğin, bir kapsayıcı türü varsa `cliext::vector<int>`, onun genel arabirim ise: `cliext::vector<int>::generic_container`. Genel arabirim üzerinden kullanarak yineleyici benzer şekilde, alabilirsiniz `generic_iterator` giriş olarak typedef: `cliext::vector<int>::generic_iterator`.  
  
 Bu tür tanımları C++ üstbilgi dosyaları bildirilir olduğundan, diğer dillerde yazılmış derlemeleri bunları kullanamazsınız. Bu nedenle, genel arabirimi erişmek için `cliext::vector<int>` , C# veya başka bir .NET dil kullanan `System.Collections.Generic.ICollection<int>`. Bu koleksiyon üzerinde döngüyle gezinmek için kullanın bir `foreach` döngü.  
  
 Aşağıdaki tabloda her STL/CLR kapsayıcı uygulayan genel arabirim listelenmektedir:  
  
|STL/CLR kapsayıcı|Genel arabirimi|  
|------------------------|-----------------------|  
|deque < T\>|ICollection < T\>|  
|hash_map < K, V >|IDictionary < K, V >|  
|hash_multimap < K, V >|IDictionary < K, V >|  
|hash_multiset < T\>|ICollection < T\>|  
|hash_set < T\>|ICollection < T\>|  
|Liste < T\>|ICollection < T\>|  
|< K, V > eşleme|IDictionary < K, V >|  
|multimap < K, V >|IDictionary < K, V >|  
|multiset < T\>|ICollection < T\>|  
|ayarlama < T\>|ICollection < T\>|  
|Vector < T\>|ICollection < T\>|  
  
> [!NOTE]
>  Çünkü `queue`, `priority_queue`, ve `stack` kapsayıcıları yineleyiciler desteklemez, genel arabirimler kullanılmaz ve erişilen çapraz derleme olamaz.  
  
## <a name="example-1"></a>Örnek 1  
  
### <a name="description"></a>Açıklama  
 Bu örnekte, özel STL/CLR üye verileri içeren bir C++ sınıf bildirin. Biz, ardından özel koleksiyonlar sınıfının erişim vermek için genel yöntemler bildirin. Biz, iki farklı şekilde, C++ istemciler için diğeri diğer .NET istemcileri için yapın.  
  
### <a name="code"></a>Kod  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
## <a name="example-2"></a>Örnek 2  
  
### <a name="description"></a>Açıklama  
 Bu örnekte, örnek 1'de bildirilen sınıfı uygulayın. Bildirim aracı kullandığımız Bu sınıf kitaplığı kullanmak istemcileri için sırayla **mt.exe** DLL'e bildirim dosyası eklemek için. Kod açıklamaları Ayrıntılar için bkz.  
  
 Bildirim aracı ve yan yana derlemeler hakkında daha fazla bilgi için bkz: [C/C++ yalıtılmış uygulamaları oluşturma ve yan yana derlemeler](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md).  
  
### <a name="code"></a>Kod  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
## <a name="example-3"></a>Örnek 3  
  
### <a name="description"></a>Açıklama  
 Bu örnekte, örnekler 1 ve 2'de oluşturulan sınıf kitaplığı kullanan C++ istemci oluşturun. Bu istemcinin kullandığı `generic_container` TypeDef içeriklerini görüntülenecek ve kapsayıcıları yineleme STL/CLR kapsayıcı.  
  
### <a name="code"></a>Kod  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
### <a name="output"></a>Çıkış  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
## <a name="example-4"></a>Örnek 4  
  
### <a name="description"></a>Açıklama  
 Bu örnekte, örnekler 1 ve 2'de oluşturulan sınıf kitaplığını kullanan bir C# istemci oluşturun. Bu istemcinin kullandığı <xref:System.Collections.Generic.ICollection%601> STL/CLR kapsayıcıları kapsayıcıları yineleme ve içeriklerini görüntülemek için yöntemleri.  
  
### <a name="code"></a>Kod  
  
```  
// CsConsoleApp.cs  
// compile with: /r:Microsoft.VisualC.STLCLR.dll /r:StlClrClassLibrary.dll /r:System.dll  
  
using System;  
using System.Collections.Generic;  
using StlClrClassLibrary;  
using cliext;  
  
namespace CsConsoleApp  
{  
    class Program  
    {  
        static int Main(string[] args)  
        {  
            StlClrClass theClass = new StlClrClass();  
  
            Console.WriteLine("cliext::deque contents:");  
            ICollection<char> iCollChar = theClass.GetDequeCs();  
            foreach (char c in iCollChar)  
            {  
                Console.WriteLine(c);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::list contents:");  
            ICollection<float> iCollFloat = theClass.GetListCs();  
            foreach (float f in iCollFloat)  
            {  
                Console.WriteLine(f);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::map contents:");  
            IDictionary<int, string> iDict = theClass.GetMapCs();  
            foreach (KeyValuePair<int, string> kvp in iDict)  
            {  
                Console.WriteLine("{0} {1}", kvp.Key, kvp.Value);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::set contents:");  
            ICollection<double> iCollDouble = theClass.GetSetCs();  
            foreach (double d in iCollDouble)  
            {  
                Console.WriteLine(d);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::vector contents:");  
            ICollection<int> iCollInt = theClass.GetVectorCs();  
            foreach (int i in iCollInt)  
            {  
                Console.WriteLine(i);  
            }  
            Console.WriteLine();  
  
            return 0;  
        }  
    }  
}  
```  
  
### <a name="output"></a>Çıkış  
  
```  
cliext::deque contents:  
a  
b  
  
cliext::list contents:  
3.14159  
2.71828  
  
cliext::map contents:  
0 Hello  
1 World  
  
cliext::set contents:  
2.71828  
3.14159  
  
cliext::vector contents:  
10  
20  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [STL/CLR Kitaplık Başvurusu](../dotnet/stl-clr-library-reference.md)