source "https://rubygems.org"
# Só é necessário para ver o site no seu computador antes de publicar.
gem "github-pages", group: :jekyll_plugins
gem "webrick"
# Bibliotecas que saíram do Ruby padrão (necessárias no Ruby 3.4+)
gem "csv"
gem "base64"
gem "bigdecimal"
gem "logger"

# Compatibilidade: o Liquid antigo do github-pages chama `tainted?`/`untaint`,
# que não existe mais no Ruby 3.2+. Só afeta o site rodando localmente.
::Object.class_eval do
  define_method(:tainted?) { false } unless method_defined?(:tainted?)
  define_method(:untaint) { self } unless method_defined?(:untaint)
  define_method(:taint) { self } unless method_defined?(:taint)
end
