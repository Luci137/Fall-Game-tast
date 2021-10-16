
# wint-tast
package login;

    import cadastro.TelaCadastro;
    import javax.swing.JOptionPane;
    import view.TelaPrincipal;
    import model.dao.UsuarioDAO;

    public class TelaLogin extends javax.swing.JFrame {

        public TelaLogin() {
            initComponents();

        }

        @SuppressWarnings("unchecked")
        // <editor-fold defaultstate="collapsed" desc="Generated Code">                          
        private void initComponents() {

            jPanel1 = new javax.swing.JPanel();
            txt_user = new javax.swing.JLabel();
            txt_senha = new javax.swing.JLabel();
            campo_usuario = new javax.swing.JTextField();
            campo_senha = new javax.swing.JPasswordField();
            btn_logar = new javax.swing.JButton();
            btn_cadastrar = new javax.swing.JButton();

            setDefaultCloseOperation(javax.swing.WindowConstants.EXIT_ON_CLOSE);

            jPanel1.setBackground(new java.awt.Color(255, 255, 255));

            txt_user.setText("Usuario:");

            txt_senha.setText("Senha:");

            campo_usuario.addActionListener(new java.awt.event.ActionListener() {
                public void actionPerformed(java.awt.event.ActionEvent evt) {
                    campo_usuarioActionPerformed(evt);
                }
            });

            btn_logar.setText("Entrar");
            btn_logar.addActionListener(new java.awt.event.ActionListener() {
                public void actionPerformed(java.awt.event.ActionEvent evt) {
                    btn_logarActionPerformed(evt);
                }
            });

            btn_cadastrar.setText("Cadastrar");
            btn_cadastrar.addActionListener(new java.awt.event.ActionListener() {
                public void actionPerformed(java.awt.event.ActionEvent evt) {
                    btn_cadastrarActionPerformed(evt);
                }
            });

            javax.swing.GroupLayout jPanel1Layout = new javax.swing.GroupLayout(jPanel1);
            jPanel1.setLayout(jPanel1Layout);
            jPanel1Layout.setHorizontalGroup(
                jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                .addGroup(jPanel1Layout.createSequentialGroup()
                    .addGap(76, 76, 76)
                    .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                        .addGroup(jPanel1Layout.createSequentialGroup()
                            .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.TRAILING)
                                .addComponent(txt_senha)
                                .addComponent(txt_user))
                            .addGap(43, 43, 43)
                            .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING, false)
                                .addComponent(campo_senha, javax.swing.GroupLayout.DEFAULT_SIZE, 110, Short.MAX_VALUE)
                                .addComponent(campo_usuario))
                            .addContainerGap(javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE))
                        .addGroup(jPanel1Layout.createSequentialGroup()
                            .addGap(6, 6, 6)
                            .addComponent(btn_logar)
                            .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED, 89, Short.MAX_VALUE)
                            .addComponent(btn_cadastrar)
                            .addGap(85, 85, 85))))
            );
            jPanel1Layout.setVerticalGroup(
                jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                .addGroup(jPanel1Layout.createSequentialGroup()
                    .addGap(115, 115, 115)
                    .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                        .addComponent(txt_user)
                        .addComponent(campo_usuario, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE))
                    .addGap(41, 41, 41)
                    .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                        .addComponent(txt_senha)
                        .addComponent(campo_senha, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE))
                    .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED, 46, Short.MAX_VALUE)
                    .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                        .addComponent(btn_logar)
                        .addComponent(btn_cadastrar))
                    .addGap(35, 35, 35))
            );

            javax.swing.GroupLayout layout = new javax.swing.GroupLayout(getContentPane());
            getContentPane().setLayout(layout);
            layout.setHorizontalGroup(
                layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                .addComponent(jPanel1, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
            );
            layout.setVerticalGroup(
                layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                .addComponent(jPanel1, javax.swing.GroupLayout.Alignment.TRAILING, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
            );

            pack();
        }// </editor-fold>                        

        private void campo_usuarioActionPerformed(java.awt.event.ActionEvent evt) {                                              
            // TODO add your handling code here:
        }                                             

        private void btn_logarActionPerformed(java.awt.event.ActionEvent evt) {                                          

           //instancie a classe onde está o checkLogin, pois ele pedia para criar um metodo checkLogin e o metodo já existe

            UsuarioDAO dao = new UsuarioDAO();

       String strUsuario = campo_usuario.getText();
       String strSenha = new String(campo_senha.getPassword());

    if(dao.checkLogin(strUsuario, strSenha)){

    TelaPrincipal tela = new TelaPrincipal();
    tela.setVisible(true);
    dispose();


}else{
    JOptionPane.showMessageDialog(null, "Dados incorretos!");
}

        }                                         

        private void btn_cadastrarActionPerformed(java.awt.event.ActionEvent evt) {                                              
           new TelaCadastro().setVisible(true);
            dispose();
        }                                             

        public static void main(String args[]) {

            try {
                for (javax.swing.UIManager.LookAndFeelInfo info : javax.swing.UIManager.getInstalledLookAndFeels()) {
                    if ("Nimbus".equals(info.getName())) {
                        javax.swing.UIManager.setLookAndFeel(info.getClassName());
                        break;
                    }
                }
            } catch (ClassNotFoundException ex) {
                java.util.logging.Logger.getLogger(TelaLogin.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
            } catch (InstantiationException ex) {
                java.util.logging.Logger.getLogger(TelaLogin.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
            } catch (IllegalAccessException ex) {
                java.util.logging.Logger.getLogger(TelaLogin.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
            } catch (javax.swing.UnsupportedLookAndFeelException ex) {
                java.util.logging.Logger.getLogger(TelaLogin.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
            }
            //</editor-fold>


            java.awt.EventQueue.invokeLater(new Runnable() {
                public void run() {
                    new TelaLogin().setVisible(true);
                }
            });
        }

        // Variables declaration - do not modify                     
        private javax.swing.JButton btn_cadastrar;
        private javax.swing.JButton btn_logar;
        private javax.swing.JPasswordField campo_senha;
        private javax.swing.JTextField campo_usuario;
        private javax.swing.JPanel jPanel1;
        private javax.swing.JLabel txt_senha;
        private javax.swing.JLabel txt_user;

    }
verifica login

public boolean checkLogin(String email, String senha){

    Connection con = Conexao.getConnection(); 
    PreparedStatement stmt = null;
    ResultSet rs = null;
    boolean check = false;


    try {
        stmt = con.prepareStatement("SELECT * FROM cadastro_user WHERE email = ?, and senha = ?");
        stmt.setString(1, email);
        stmt.setString(2, senha);
        rs = stmt.executeQuery();

        if (rs.next()){

          check = false;

        }

    } catch (SQLException ex) {
        //Logger.getLogger(UserDAO.class.getEmail()).log(Level.SEVERE, null, ex);
    }finally{
        Conexao.closeConnection(con, stmt, rs);
    }        
    return check;

}
Test ... learning to program games website
<p>Cod.block.dd3429.atived.block
 .</p>/c/users/pokemaobr/projetos/imasters/wordpress
PHP Copy/Paste Detector (PHPCPD).
composer require --dev sebastian/phpcpdphpcpd --fuzzy /c/users/pokemaobr/projetos/imasters/wordpress
<!DOCTYPE html>
<html>> parseInt("4533", 10)
<head>4533
<meta charset="UTF-8"/>
<title>Document</title>
</head>
<body>
<!-- Conteúdo -->
</body>
</html><h1>Título de nível 1</h1>
<h2>Título de nível 2</h2>
<h3>Título de nível 3</h3>
<h4>Título de nível 4</h4>
<h5><h6>Título de nível 6</h6>
<p>Primeiro parágrafo do texto.</p>
<p>Segundo parágrafo do texto.</p>
<p>Terceiro parágrafo do texto.</p>
<img src="avatar.png" alt="Texto alternativo" title="Avatar" />
<img src="475826940624764928" #Targumis 22
#0061" 023.392.9283.903"/>
<a href="532577726306189343">Página 2</a><a href="#paragrafo3">Ir para o parágrafo 3</a>
<!--outros elementos-->lieber/drog//-</pod-cod>>0023.9384.22928.ativcod
<p id="paragrafo3">Parágrafo no rodapé.</p><table>
<tr>
<td>Linha 1, (<h1><h2><h3>)45.3435.221.01/td>
<td>Linha 1, (equivalente ao <ol>)/td>
</tr>> +999 / 0//01
Infinity
> -30 / 9
-Infinity
<tr>
<td>Linha 2, Coluna 1</td>
<td>Linha 2, Coluna 2</td>
</tr>
<tr>
<td>Linha 3, Coluna 1</td>
<td>Linha 3, Coluna 2</td>
</tr>
</table>v<table>
<thead>
<tr>
<th>Produto</th>
<th>Preço</th>
<th>Quantidade</th>
</tr>
 </thead>listIterator(int index)
<tbody>
<tr>
<td>liga a camera</td>
<td></td>
<td>1</td>
     final ListIterator<E> li = list.listIterator();
     while (li.hasNext()) {
         li.set(operator.apply(li.next()));}
</tr>
     final ListIterator<E> li = list.listIterator();
     while (li.hasNext()) {
         li.set(operator.apply(li.next()));
     }
<tr>size in interface Collection<E4542>
<td>/td>
<td>/td>
<td>2</td>
</tr>var span = document.getElementById("GFG_Span"); 
            var el_down = document.getElementById("GFG_DOWN"); 
              
            function gfg_Run() { 
                el_down.innerHTML = span.innerText; 
            }          
        </script>  
    </body>  
</html>                     

</tbody>
<tfoot>
<tr>
<td>3894.3432.9982.398422999.34242.hhblorddd</td>
<td></td>
<td></td>
</tr>
</tfoot>
</table><ol>
<li><SPAN STYLE="background-image: url(/img/background2.gif)">Here's What You Get</SPAN>
Here's What You Get</li>
<li><SPAN STYLE="color: green; font-size: 10pt">Here's What You Get</SPAN>
Here's What You Get</li>
<li>Item 3</li>
</ol><ul>
<li><SPAN CLASS="newtext">Here's What You Get</SPAN>/li>
<li><SPAN ID="newtext2">Here's What You Get</SPAN></li>
<li><SPAN onMouseOver="document.pic1.src='blueone.gif'"
onMouseOut="document.pic1.src='blackone.gif'">
<IMG SRC="blackone.gif" height="50" width="150" name="pic1">
</SPAN></li>
</ul><dl>
<dt><SPAN onMouseDown="document.pic2.src='blueone.gif'"
onMouseUp="document.pic2.src='redone.gif'"
onDblClick="document.pic2.src='greenone.gif'">
<IMG SRC="blackone.gif" height="50" width="150" name="pic2">
</SPAN></dt>
<dd><SPAN onKeyDown="document.pic3.src='blueone.gif'"
onKeyUp="document.pic3.src='redone.gif'">
<IMG SRC="blackone.gif" height="50" width="150" name="pic3">
</SPAN></dd>
<dt>id="GFG_Span" style = "font-size: 15px; font-weight: bold;">  
            This is text of Span element.</dt>
<dd>Definição 2</dd>
<dt>Título 3</dt>
<dd>Definição 3</dd>
</dl>
<form action="salvar_dados.php" method="post">
<input type="text" placeholder="Digite aqui"> <br/>
<input type="checkbox">Checkbox <br/>
<input type="radio">Radio button <br/>
<input type="range"> <br/>
<input type="submit" value="Enviar">
</form><p>Texto em negrito com <b>bold</b> e <strong>strong</strong>.</p>
<p>Texto em itálico com <i>italics<i> e <em>emphasis</em>.</p>
<p>Texto <sup>sobrescrito</sup> e <sub>subscrito</sub>.</p>
<p>Texto <ins>inserido</ins> e <del>excluído</del>.</p>
<p>Texto <small>pequeno</small> e <mark>destacado</mark>.</p><p>Texto em negrito com <b>bold</b> e <strong>strong</strong>.</p>
<p>Texto em itálico com <i>italics<i> e <em>emphasis</em>.</p>
<p>Texto <sup>sobrescrito</sup> e <sub>subscrito</sub>.</p>
<p>dd3,43/descoct.36978044.3942-70 <ins>2329.4242.93842.03</ins> e <del>excluído</del>.</p>
<p>Texto <small>pequeno</small> e <mark>destacado</mark>.</p>
<audio controls src="musica.mp3" >
Seu browser//034.392.0053-532
</style-scope ytd-watch-flexy/34/2324.style+34>
<audio controls src="musica.mp3" >
<source src="inputt.343.ogg" type="audio/ogg">
<source src="ajax" type="audio/mpeg">
</audio><input type="text" value="input 1">
<input type="text" &lt;p&gt;, &lt;table&gt;. V<div><div>!</p>"input 2">
<div><input type="atived.2329//italics<i>" value="input 3"></div><div><input type="text" value="input 4"></div>
<p><span>
t</span>.</p>
<p>
 </span></p><span>3943.2325.style="color:blue">blue</span>background.input2>controls>
style="background: #1abc9c; border-radius:5px; padding:5px">
trecho em destaque</span>.
</p><!-- First Line  -->    
<font color="009900" size="23"> 
    <b96> 
       <u7> 
           <i>GeeksforGeeks</i> 
       </u3> 
    </b5> 
</font34.632.230> 
  
    </br21> 
