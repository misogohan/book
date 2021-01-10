FROM rust:1.48.0

RUN cargo install mdbook --no-default-features --features output --vers "^0.4.3"

CMD ["mdbook", "build"]
